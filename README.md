public class Main {
    public static void main(String[] args) {
        System.out.println("===== Welcome to the Java Quiz App =====");
        QuestionService service = new QuestionService();
        service.startQuiz();
        service.showResult();
    }
}
public class Question {
    int id;
    String question, option1, option2, option3, option4, correctAnswer;

    public Question(int id, String question, String option1, String option2, String option3, String option4, String correctAnswer) {
        this.id = id;
        this.question = question;
        this.option1 = option1;
        this.option2 = option2;
        this.option3 = option3;
        this.option4 = option4;
        this.correctAnswer = correctAnswer;
    }

    public void displayQuestion() {
        System.out.println(id + ". " + question);
        System.out.println("a) " + option1);
        System.out.println("b) " + option2);
        System.out.println("c) " + option3);
        System.out.println("d) " + option4);
    }
}import java.util.Scanner;

public class QuestionService {
    Question[] questions = new Question[5];
    String[] answers = new String[5];

    public QuestionService() {
        questions[0] = new Question(1, "What is the size of int in Java?", "2", "4", "8", "1", "b");
        questions[1] = new Question(2, "Which keyword is used to inherit a class in Java?", "this", "super", "extends", "implements", "c");
        questions[2] = new Question(3, "Which method is the entry point of Java program?", "main()", "start()", "run()", "init()", "a");
        questions[3] = new Question(4, "What is the default value of a boolean variable?", "true", "false", "0", "null", "b");
        questions[4] = new Question(5, "Which is not a Java keyword?", "class", "interface", "goto", "unsigned", "d");
    }

    public void startQuiz() {
        Scanner sc = new Scanner(System.in);
        for (int i = 0; i < questions.length; i++) {
            questions[i].displayQuestion();
            System.out.print("Your answer (a/b/c/d): ");
            answers[i] = sc.next();
            System.out.println();
        }
    }

    public void showResult() {
        int score = 0;
        System.out.println("------ Result ------");
        for (int i = 0; i < questions.length; i++) {
            System.out.println("Q" + (i + 1) + ": " + (answers[i].equalsIgnoreCase(questions[i].correctAnswer) ? "Correct" : "Wrong"));
            if (answers[i].equalsIgnoreCase(questions[i].correctAnswer)) {
                score++;
            }
        }
        System.out.println("Your Score: " + score + "/" + questions.length);
    }
}

