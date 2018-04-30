---
layout: post
title: Find max and min lexical substrings of a string
category: 算法
keywords: /blog_accessary/blog_images/hackerrank/open.png
date: 2018-04-28 16:09:02
---

```java
public class Solution {
    public static Scanner in = new Scanner(System.in);

    public static String readString() {
        return in.nextLine();
    }


    public static void output(String string) {
        System.out.println(string);
    }

    public static Pattern createPattern(String pattern) {
        return Pattern.compile(pattern);
    }

    public static boolean isALexicallyBiggerThanB(String a, String b) {
        return a.compareTo(b) > 0;
    }

    public static List<String> getAllOrderedStringComponentOfAString(String str1, int compnentSize) {
        List<String> strings = new ArrayList<String>();
        int startingPosition;
        for (startingPosition = 0; startingPosition + compnentSize <= str1.length(); startingPosition++) {
            strings.add(str1.substring(startingPosition, startingPosition + compnentSize));
        }
        return strings;
    }

    public static void main(String[] args) {
        String inputStr1 = readString();
        int componentSize = readInt();
        List<String> orderedComponentStrs = getAllOrderedStringComponentOfAString(inputStr1, componentSize);
        String biggestLexicalString = orderedComponentStrs.get(0);
        String smallestLexicalString = orderedComponentStrs.get(0);
        for (int i = 0; i < orderedComponentStrs.size(); i++) {
            biggestLexicalString = (isALexicallyBiggerThanB(biggestLexicalString, orderedComponentStrs.get(i))) ? biggestLexicalString:orderedComponentStrs.get(i);
            smallestLexicalString = (isALexicallyBiggerThanB(smallestLexicalString, orderedComponentStrs.get(i))) ? orderedComponentStrs.get(i):smallestLexicalString;

        }
        output(smallestLexicalString);
        output(biggestLexicalString);

    }
}
```

Good habit:

1.  SRP,each functions have own responsibility and it is short enough.
2.  Reuse,the isALexicallyBiggerThanB is written in another solution before.

Improvements that can be made:

1.  Naming of getAllOrderedStringComponentOfAString,however the **StringComponent** can be called as **substring**.
    It is unnecessary to create a entire new name.
    It is a noise words that create meaningless distinction.**([clean code uncle bob](http://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882))**

We should change better name when you find a new one.So solve the problem and post your better solution =>. [Problem at hackerrank](https://www.hackerrank.com/challenges/java-string-compare)

Or make a pull request to [My github for hackerrank](https://github.com/chungchi300/hackerrank)
