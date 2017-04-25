## Java truncate text

* sample 1

```bash
String FullName = "Bill Gates";
String FirstNameChars = "";

FirstNameChars = FullName.substring( 0, 2 );
```

* sample 2

```bash
package com.bashan.blog.string;

public class StringUtils {

  public static String truncateText(String str, int maxLen, int lenFromEnd) {

    int len;

    if (str != null && (len = str.length()) > maxLen) {

      return str.substring(0, maxLen - lenFromEnd - 3) + "..." +

          str.substring(len - lenFromEnd, len);

    }

    return str;

  }

  public static String truncateText(String str, int maxLen) {

    return truncateText(str, maxLen, 0);

  }

  public static void main(String[] args) {

    String str = "This is some long text test, This is some long text test, This is some long text test";

    System.out.println(truncateText(str, 30, 12));

    System.out.println(truncateText(str, 30));

  }

}
```