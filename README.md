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
}
