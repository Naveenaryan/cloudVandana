# cloudVandana
Java:
1.Create an array with the values (1, 2, 3, 4, 5, 6, 7) and shuffle it.

import java.util.Random;

public class ShuffleArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5, 6, 7};
        shuffleArray(array);
        
        // Print the shuffled array
        for (int i = 0; i < array.length; i++) {
            System.out.print(array[i] + " ");
        }
    }

    public static void shuffleArray(int[] array) {
        int n = array.length;
        Random random = new Random();
        
        for (int i = n - 1; i > 0; i--) {
            int j = random.nextInt(i + 1);
            
            // Swap array[i] and array[j]
            int temp = array[i];
            array[i] = array[j];
            array[j] = temp;
        }
    }
}


2.Enter a Roman Number as input and convert it to an i nteger. ( Example: IX = 9)

class Solution {
    public int romanToInt(String s) {
        Map<Character, Integer> map = new HashMap();
            map.put('I', 1);
            map.put('V', 5);
            map.put('X', 10);
            map.put('L', 50);
            map.put('C', 100);
            map.put('D', 500);
            map.put('M', 1000);

            int result = 0;
            for (int i = 0; i < s.length(); i++) {
                if (i > 0 && map.get(s.charAt(i)) > map.get(s.charAt(i - 1))) {
                    result += map.get(s.charAt(i)) - 2 * map.get(s.charAt(i - 1));
                } else {
                    result += map.get(s.charAt(i));
                }
            }
            return result;
    }
}

3.Check if the input is pangram or not. (A pangram is a sentence that contains all the 
Alphebets from A to Z

import java.util.Scanner;

public class PangramCheck {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a sentence: ");
        String input = scanner.nextLine();
        scanner.close();

        if (isPangram(input)) {
            System.out.println("The input is a pangram.");
        } else {
            System.out.println("The input is not a pangram.");
        }
    }

    public static boolean isPangram(String sentence) {
        // Create an array to mark the presence of each letter
        boolean[] alphabet = new boolean[26];

        // Convert the sentence to lowercase to handle both cases
        sentence = sentence.toLowerCase();

        for (int i = 0; i < sentence.length(); i++) {
            char currentChar = sentence.charAt(i);

            // Check if the character is an alphabet letter
            if ('a' <= currentChar && currentChar <= 'z') {
                int index = currentChar - 'a';
                alphabet[index] = true;
            }
        }

        // Check if all letters from 'a' to 'z' are marked as true
        for (boolean letterPresent : alphabet) {
            if (!letterPresent) {
                return false;
            }
        }

        return true;
    }
}

Java Script:

1.Take a sentence as an input and reverse every word in that sentence.

// Function to reverse a word
function reverseWord(word) {
    let reversed = '';
    for (let i = word.length - 1; i >= 0; i--) {
        reversed += word[i];
    }
    return reversed;
}

// Take input from the user
const sentence = prompt("Enter a sentence:");

// Split the sentence into words
const words = sentence.split(" ");

// Reverse each word and store the result in a new array
const reversedWords = [];
for (let i = 0; i < words.length; i++) {
    reversedWords.push(reverseWord(words[i]));
}

// Join the reversed words to form the reversed sentence
const reversedSentence = reversedWords.join(" ");

// Display the reversed sentence
console.log("Reversed Sentence: " + reversedSentence);


2.Perform sorting of an array in descending order.

const arr = [5, 2, 9, 1, 5, 6];

// Sort the array in descending order
arr.sort(function(a, b) {
    return b - a;
});

console.log("Sorted array in descending order: " + arr);

project.1

<!DOCTYPE html>
<html>

<head> <link rel="stylesheet" href="index.css">
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0" >
<meta name="robots" content="none,noarchive"/>
</head>

<body>
    <div class="bg-container d-flex">
        <div class="calculator">
            <div class="input-result-container">
                <input type="text" id="display" disabled>
                <button class="clear-btn" onclick="clearDisplay()">AC</button>
            </div>
            <div class="button-section">
                <div class="numbers">
                    <div>
                        <button class="button" onclick="appendToDisplay('9')">9</button>
                        <button class="button" onclick="appendToDisplay('8')">8</button>
                        <button class="button" onclick="appendToDisplay('7')">7</button>
                    </div>
                    <div>
                        <button class="button" onclick="appendToDisplay('4')">4</button>
                        <button class="button" onclick="appendToDisplay('5')">5</button>
                        <button class="button" onclick="appendToDisplay('6')">6</button>
                    </div>
                    <div>
                        <button class="button" onclick="appendToDisplay('1')">1</button>
                        <button class="button" onclick="appendToDisplay('2')">2</button>
                        <button class="button" onclick="appendToDisplay('3')">3</button>
                    </div>
                    <div>
                        <button class="button" onclick="appendToDisplay('.')">.</button>
                        <button class="button" onclick="appendToDisplay('0')">0</button>
                        <button class="button" onclick="calculate()">=</button>
                    </div>
                </div>
                <div class="mathematical-symbols">
                    <button class="button" onclick="appendToDisplay('+')">+</button>
                    <button class="button" onclick="appendToDisplay('-')">-</button>
                    <button class="button" onclick="appendToDisplay('/')">/</button>
                    <button class="button" onclick="appendToDisplay('*')">x</button>
                </div>
            </div>
        </div>
    </div>
<script src="index.js"></script>
</body>

</html>

project.2



<!DOCTYPE html>
<html>

<head>
    <title>Survey Form</title>
    <link rel="stylesheet" type="text/css" href="survey_form.css">
<link rel="stylesheet" href="index.css">
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0" >
<meta name="robots" content="none,noarchive"/>
</head>

<body>
    <div class="bg-container">
        <form>
            <div class="bg-container">
                <h1 class="heading">Customer Survey Form</h1>
                <div class="card-container">
                    First Name <input id="FirstName" type="text" required><br>

                    Last Name <input id="LastName" type="text" required><br>
                    Date Of Birth <input id="BirthDate" type="date" required><br>
                    Country <select required>
                        <option>select</option>
                        <option>india</option>
                        <option>nepal</option>
                        <option>srilanka</option>
                        <option>bangladesh</option>
                    </select><br>
                    <div class="gender">
                        Gender <input type="checkbox"> MAle
                        <input type="checkbox"> Female

                    </div>
                    <br>Profession <input required />
                    <br>Email <input type="email" required>
                    <br>Mobile <input type="number" maxlength="10" required>

                    <br>
                    <div class="division">
                        <button onclick="button1()" class="submitbutton">Submit</button>
                        <br>
                        <button onclick="button2()" class="resetbutton">Reset</button>

                    </div>

                </div>
                <div class="icon-container">
                    <p class="lower ">Customer Survey Form. All Rights Reserved | Design by </p>
                    <p class="icon "> W3Layouts</p>
                </div>
            </div>
        </form>

    </div>

<script src="index.js"></script>
</body>

</html>

