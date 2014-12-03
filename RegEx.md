# General resources

[Site that lets you preview your RegEx](http://www.regexr.com/)



----------------------------
# Resources that need to be edited

Rubular: a Ruby regular expression editor and tester 
http://rubular.com/
coding  regex  review  
2014.10.17   13:45:33 by HM0880   edit   delete
✭ ***RegExr: Learn, Build, & Test RegEx 
http://www.regexr.com/
coding  regex  resources  ongithub  
2014.10.17   13:45:28 by HM0880   edit   delete
✭ TechnoCrat: Useful Regular Expressions for Notepad++ 
http://javakafunda.blogspot.com/2011/11/useful-regular-expressions-for-notepad.html
Adding a semicolon to each line where it doesn't end with semicolon 
Adding a particular line before each line 
Append * to end of each line 
Remove * from end of each line 
Change MM by dd or dd by MM in a date 
Remove C++ comments from the file 
Removing the preceding numbers from each line 
Removing the lines which do not contain dot (.) character
regex  
2014.08.03   18:26:22 by HM0880   edit   delete
✭ Regex Find/Replace in Notepad++ - Stack Overflow 
http://stackoverflow.com/questions/20286068/regex-find-replace-in-notepad
Note: I used "\1" (no quotes) instead of "$1" for a group capture.

------------------------------------------

In Notepad++ to replace, hit Ctrl+H to open the Replace menu.

Then if you check the "Regular expression" button and you want in your replacement to use a part of your matching pattern, you must use "capture groups" (read more on google). For example, let's say that you want to match each of the following lines

value="4"
value="403"
value="200"
value="201"
value="116"
value="15"

using the .*"\d+" pattern and want to keep only the number. You can then use a capture group in your matching pattern, using parentheses ( and ), like that: .*"(\d+)". So now in your replacement you can simply write $1, where $1 references to the value of the 1st capturing group and will return the number for each successful match. If you had two capture groups, for example (.*)="(\d+)", $1 will return the string value and $2 will return the number.

So by using:

Find: .*"(\d+)"

Replace: $1

It will return you

4
403
200
201
116
15

Please note that there many alternate and better ways of matching the aforementioned pattern. For example the pattern value="([0-9]+)" would be better, since it is more specific and you will be sure that it will match only these lines. It's even possible of making the replacement without the use of capture groups, but this is a slightly more advanced topic, so I'll leave it for now :)
regex  
2014.08.03   18:24:42 by HM0880   edit   delete
✭ Understanding RegEx with Notepad++ 
http://blog.creativeitp.com/posts-and-articles/editors/understanding-regex-with-notepad/
Regex characters can be used to create advanced matching criteria. The following table introduces some of them with practical examples. But before starting make sure that you change the Search Mode from Normal to Regular expression in your Find or Find & Replace dialogue box. 

[ ] 
The square brackets can be used to match ONE of multiple characters. For instance, [abc] matches any of the characters a, b or c. Hence, b[eo]n will match words like ben and bon, but not been or beon. Ranges can also be used, [a-z] is any lower case character and so on. 

^ 
The caret can be used inside the square brackets to exclude characters from the match. For instance, hell[^o] means the string ‘hell’ will be ignored if followed by the letter ‘o’. Another example is [^A-Za-z] which will exclude all alphabetic characters. 
However, if not placed inside a set, ^ can be used to matches the start of a line. 

$ 
This matches the end of a line. 

. 
The period or dot matches any character. 

\d 
Matches any single digit. 

\w 
Matches any single alphanumeric characters or underscore. 

\s 
Matches whitespaces including tabs and line breaks. 

* 
The asterisk or star sign matches 0 or more times. For example, Ba*m matches Bm , Bam , Baam etc.

+ 
The plus sign matches 1 or more times. For example, lo+l matches lol , lool , loool etc. 

\< 
Matches the start of a word. For example, \< directly followed by 'sh' matches 'she' but does not matches 'wish'. 

\> 
Matches the end of a word. For example, sh\> matches ‘wish’ and does not matches ‘she’. 

( ) 
The round brackets can be used in the Find & Replace function to tag a match. tagged matches can then be used in replace with \1, \2 etc. 

For example, If you write 123xxxRRR in the search and 123\1HHH in the ‘Replace with’ filed, the result will be: 123xxxHHH. 

\ 
The backslash can be used to escape regex characters. For example to match 1+1=2, the correct regex is 1\+1=2. Otherwise, the plus sign will have a special meaning. 

Further, the following two examples should be giving you a better idea of how to use regex in your editor: 

Find: Win([0-9]+) Replace with: Windows\1 
Will search for strings like Win2000, Win2003 and changes them to Windows2000, Windows2003… 

Find: [a-z]+(\d\d)\> Replace with: Windows\1 
Will search for all alphanumerics followed by 2 digits only at the end such as Win98 and Win07 and changes them to Windows98, Windows07…
regex  
2014.08.03   18:17:25 by HM0880   edit   delete
✭ The Power of Regular Expression: use in notepad++ 
http://www.slideshare.net/anjesh/the-power-of-regular-expression-use-in-notepad/
slideshow about regex
regex  
2014.08.03   18:16:14 by HM0880   edit   delete
✭ Mark's Speechblog: Notepad++: A guide to using regular expressions and extended search mode 
http://markantoniou.blogspot.com/2008/06/notepad-how-to-use-regular-expressions.html
lots of detail about regex. could be very useful in the future.
regex  
2014.08.03   18:15:46 by HM0880   edit   delete
✭ Word: Replace and reformat text inside square brackets using wildcards 
http://cybertext.wordpress.com/2011/06/20/word-replace-and-reformat-text-inside-square-bra…
Type the following exactly (or copy it from here): (\[)(*)(\])
Go to the Replace with field and type: \1\2\3
Click the Format button, and select Font.
On the Font dialog box change the settings to what you want — in my husband’s case, this was 4 pt and blue — then click OK. Your Find and Replace dialog box should now look like this:
Find and reformat text inside square brackets
Find and reformat text inside square brackets
Click Replace All.
Once all replacements have been made, check that you got what you expected before making further changes to the document. If it’s all OK, save your document with the new changes.
What it all means
The three elements of the Find are:

(\[) — You need to find a specific character (the opening square bracket), so you need to enclose it in parentheses. However, because the square brackets are special wildcard characters in their own right, you need to tell Word to treat them as normal text characters and not as special characters, so you put in a backslash ‘\‘ (also known as an ‘escape’ character) before the [.
(*) -- This tells Word to look for any characters after the opening square bracket. There's no limit on what sort of characters (alpha, numeric, or symbols) Word is to find, or on how many there are.
(\]) — This tells Word to stop the find at the first closing square bracket it finds after an opening square bracket followed by any other characters. As with the opening square bracket (1. above), the closing square bracket is a special wildcard character, so needs a backslash in front of it for Word to treat it as ordinary text, and it needs to be enclosed in parentheses as it’s an exact match you want.
There are no spaces between any of these elements — the aim is to find a string such as [green frog] and replace it with exactly the same text but formatted in a different color and with a difference font size.

The three elements of the Replace are:

\1 — Tells Word to replace the first element of the Find with what was in the Find (the opening square bracket).
\2 — Tells Word to replace the second element of the Find with the same text as what was found. In other words, keep the exact text as was found, but change it’s font size and color.
\3 — Tells Word to replace the third element of the Find with what was in the Find (the closing square bracket).
As with the Find elements, there are no spaces between these elements. You still want [green frog], not [ green frog ].
regex  resources  
2014.08.03   16:01:01 by HM0880   edit   delete
