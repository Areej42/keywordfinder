import java.util.*;
import java.util.regex.*;

public class Main {
    // Java keywords regex pattern
    private static final String KEYWORD_REGEX = "\\b(boolean|break|byte|case|catch|char|class|const|continue|default|do|double|else|float|for|goto|if|int|interface|long|native|new|package|private|protected|public|return|short|static|super|switch|synchronized|this|throw|throws|transient|try|void|volatile|while)\\b";

    public static void main(String[] args) {
        // Sample Java code
        String code = """
            public class Comment {
                public static void main(String[] args) {
                    int a = 3;
                    int b = 2;
                    int sum = a + b;
                    System.out.println(sum);
                }
            }
        """;

        // Compile the regex pattern
        Pattern pt = Pattern.compile(KEYWORD_REGEX);

        // Matcher to find keywords in the code
        Matcher mt = pt.matcher(code);

        // Check if any Java keywords are found
        boolean matchFound = false;

        // Find all matches and print them
        while (mt.find()) {
         //   System.out.println("Keyword found: " + mt.group());
           matchFound = true;
            System.out.println(mt.group());
        }


        // If no keyword was found, print an invalid input message
        if (!matchFound) {
            System.out.println("No Java keywords found");
        }
    }
}
