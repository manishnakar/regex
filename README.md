# Regular expressions

##1. Matching a single character
     
    * The dot (.) matches any character. If you want to match the dot as a character, escape it like this: \.
    * A question mark (?) means that the preceding character is optional. If you want to match an actual question mark, escape it: \?

          var text = 'Lorem ipsum dolor sit amet, consectetur adipiscing elit lest. Donec convallis dignissim ligula, et rutrum est elat vistibulum eu.';
          
          // Will match both "elit" and "elat". The dot can match any character.
          // Tip: try removing the "g" modifier of the regex to see what happens.
          
          var regex = /el.t/g;
           text.match(regex);
          
          // Will match both "est" and "lest". The question mark makes "l" optional.
          
          var regex2 = /l?est/g;
          text.match(regex2);


##2. Matching a character of a set

  
    A set is one or more characters enclosed in brackets [abc]. It matches only one of those characters – in this example only a, b or c. You can negate a set with ^. [^abc] will match any character that is not a, b or c. You can also specify a range [0-9], [a-z], which will match everything in the range.
    There are built-in sets that make writing regexes easier (they are called shorthand). Instead of [0-9] you can write \d and for [^0-9] you can write \D. There are also sets for word characters (a through z with digits and underscore) – \w and \W, and spaces (including tabs and new lines) - \s and \S.


##3. Matching words


    +, which repeats the preceding character or set one or more times
    *, which repeats the preceding character or set zero or more times
    {x} for an exact number of repetitions, {x,y} for varying number of repetitions (where x and y are numbers)

Also, there is the special \b pattern which matches the boundaries at the ends of words (not a real symbol).

##4. Matching/validating entire lines
 Start and end of the text using ^ (start of line), $ (end of line) expressions.
 
 
##5. Search and replace

    A group is a set of patterns enclosed in braces (). Each group collects the text that was matched by the patterns inside it. The text matched by each group can be addressed later with indexes prefixed with dollar signs (starting from $1 for the first group).
    Each group is available in the pattern itself as a back reference – backward slash followed by the group index, starting from \1 (see the example below). This is only rarely used, so you can blissfully forget about this feature.

 
