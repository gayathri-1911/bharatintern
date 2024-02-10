# bharatintern
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
import java.util.Scanner;

class QuizApp {
    static class Question {
        String prompt;
        String answer;

        Question(String prompt, String answer) {
            this.prompt = prompt;
            this.answer = answer;
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        List<Question> questions = new ArrayList<>();
        questions.add(new Question("What is the capital of France?", "Paris"));
        questions.add(new Question("Which planet is known as the Red Planet?", "Mars"));
        questions.add(new Question("What is the largest mammal on Earth?", "Blue Whale"));
        questions.add(new Question("What is the powerhouse of the cell?", "Mitochondria"));
        questions.add(new Question("Which gas is most abundant in Earth's atmosphere?", "Nitrogen"));
        questions.add(new Question("Who wrote 'Romeo and Juliet'?", "William Shakespeare"));
        questions.add(new Question("What is the square root of 144?", "12"));
        questions.add(new Question("Which country is known as the 'Land of the Rising Sun'?", "Japan"));
        questions.add(new Question("What is the currency of Brazil?", "Brazilian Real"));
        questions.add(new Question("Who painted the Mona Lisa?", "Leonardo da Vinci"));
        questions.add(new Question("What is the largest ocean on Earth?", "Pacific Ocean"));
        questions.add(new Question("In what year did the Titanic sink?", "1912"));
        questions.add(new Question("What is the capital of Japan?", "Tokyo"));
        questions.add(new Question("Who wrote 'To Kill a Mockingbird'?", "Harper Lee"));
        questions.add(new Question("What is the speed of light?", "299,792 kilometers per second"));
        questions.add(new Question("Which element has the chemical symbol 'O'?", "Oxygen"));
        questions.add(new Question("What is the boiling point of water in Celsius?", "100 degrees"));
        questions.add(new Question("Who discovered penicillin?", "Alexander Fleming"));
        questions.add(new Question("What is the currency of India?", "Indian Rupee"));
        questions.add(new Question("How many continents are there on Earth?", "7"));

        // Shuffle the questions to make them non-repeated
        Collections.shuffle(questions);

        int correctAnswers = 0;
        int totalQuestions = questions.size();

        System.out.println("Welcome to the Quiz App!");

        while (true) {
            for (int i = 0; i < totalQuestions; i++) {
                Question currentQuestion = questions.get(i);
                System.out.println("Question " + (i + 1) + ": " + currentQuestion.prompt);
                System.out.print("Your answer: ");
                String userAnswer = scanner.nextLine();

                if (userAnswer.equalsIgnoreCase(currentQuestion.answer)) {
                    System.out.println("Correct!\n");
                    correctAnswers++;
                } else {
                    System.out.println("Incorrect. The correct answer is: " + currentQuestion.answer + "\n");
                }
            }

            System.out.println("Quiz completed! Your Results:");
            System.out.println("Correct Answers: " + correctAnswers);
            System.out.println("Incorrect Answers: " + (totalQuestions - correctAnswers));

            System.out.print("Do you want to quit? (yes/no): ");
            String quitChoice = scanner.nextLine().toLowerCase();

            if (quitChoice.equals("yes")) {
                break;
            } else {
                // Shuffle questions for the next round
                Collections.shuffle(questions);
            }
        }

        System.out.println("Thank you for playing the Quiz App!");
    }
}

