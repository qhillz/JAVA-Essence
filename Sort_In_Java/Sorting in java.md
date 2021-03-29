# Sorting in java

**There are two in-built methods** to sort in JAVA.

-- TimSorting 기반.  ===> **Best : O(n)** / **Worst : O(nlogn)**

1. Arrays.sort(),  원시 타입 배열에 해당되는 솔팅 

   * ``` java 
     // A sample Java program to demonstrate working of
     // Arrays.sort().
     // It by default sorts in ascending order.
     import java.util.Arrays;
       
     public class GFG {
         public static void main(String[] args)
         {
             int[] arr = { 13, 7, 6, 45, 21, 9, 101, 102 };
       
             Arrays.sort(arr);
       
             System.out.printf("Modified arr[] : %s",
                               Arrays.toString(arr));
         }
     }
     ```

2. Collections.sort(), 컬렉션에 해당되는 솔팅

   * ``` java
     // Java program to demonstrate working of Collections.sort()
     import java.util.*;
       
     public class GFG {
         public static void main(String[] args)
         {
             // Create a list of strings
             ArrayList<String> al = new ArrayList<String>();
             al.add("Geeks For Geeks");
             al.add("Friends");
             al.add("Dear");
             al.add("Is");
             al.add("Superb");
       
             /* Collections.sort method is sorting the
             elements of ArrayList in ascending order. */
             Collections.sort(al);
       
             // Let us print the sorted list
             System.out.println("List after the use of"
                                + " Collection.sort() :\n" + al);
         }
     }
     ```



## 리버스 솔팅

(1) **Arrays.sort(배열, Collections.reverseOrder())**;

(2) **Collections.sort(배열, Collections.reverseOrder())**;



## Collections.sort에 관한 정보.

``` typescript
public static void sort(List myList)

myList : A List type object we want to sort.

This method doesn't return anything
```

* This class consists exclusively of static methods that operate on or return collections.  It contains polymorphic algorithms that operate on collections, "wrappers", which return a new collection backed by a specified collection, and a few other odds and ends. 

  * 결과적으로, Java.util패키지의 Collections클래스의 public abstract sort 메소드가 기능을 운영한다.

    ### 중요사항 

  * **All elements in the list must implement the Comparable interface. Furthermore, all elements in the list must be mutually comparable (that is, e1.compareTo(e2))**

    * 예를 들어, ArrayList안의 값이 제내릭 설정이 안돼서 다양한 타입의 Object를 품고 있다면 Comparable 하지 못하기 때문에 오류가 난다.
    * ![Java 객체 정렬과 비교](https://media.vlpt.us/images/agugu95/post/a43189f8-835e-406b-af21-6ffe68188552/image.png)

    **List의 값은 Comparable을 Implement한 원소이어야 하는게 또한 조건.**

    **Comparable 인터페이스는 compareTo() 메소드를 소지하며 이를 각 Class는 적절하게 오버라이딩 하였고 더불어 나가서, 사용자가 재정의해서 사용 가능하다.** 

    **궁극적으로, Collections.sort()는 Comparable<Interface>에서 형태가 제공된 compareTo()를 오버라이딩한 List의 원소에 의존하여 정렬을 진행한다.**

    * ```java
      // A Java program to demonstrate use of Comparable
      import java.io.*;
      import java.util.*;
       
      // A class 'Movie' that implements Comparable
      class Movie implements Comparable<Movie>
      {
          private double rating;
          private String name;
          private int year;
       
          // Used to sort movies by year
          public int compareTo(Movie m)
          {
              return this.year - m.year;
          }
       
          // Constructor
          public Movie(String nm, double rt, int yr)
          {
              this.name = nm;
              this.rating = rt;
              this.year = yr;
          }
       
          // Getter methods for accessing private data
          public double getRating() { return rating; }
          public String getName()   {  return name; }
          public int getYear()      {  return year;  }
      }
       
      // Driver class
      class Main
      {
          public static void main(String[] args)
          {
              ArrayList<Movie> list = new ArrayList<Movie>();
              list.add(new Movie("Force Awakens", 8.3, 2015));
              list.add(new Movie("Star Wars", 8.7, 1977));
              list.add(new Movie("Empire Strikes Back", 8.8, 1980));
              list.add(new Movie("Return of the Jedi", 8.4, 1983));
       
              Collections.sort(list);
       
              System.out.println("Movies after sorting : ");
              for (Movie movie: list)
              {
                  System.out.println(movie.getName() + " " +
                                     movie.getRating() + " " +
                                     movie.getYear());
              }
          }
      }
      ```

## Comparable VS Comparator

* 공통적인 점은, 둘 다 인터페이스이며 Collections.sort()의 정렬 방법을 결정한다.

### 정의 비교 

​	(From Comparable)

**int compareTo(Object obj)** **:** This method compares this String to another Object.

​	(From Comparator)

**public int compare(Object obj1, Object obj2)**


