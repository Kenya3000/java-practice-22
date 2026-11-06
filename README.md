# java-practice-22
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class  main {
    public static void main(String[] args) {
        List<String> tasks = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);
        boolean work = true;

        while (work) {
            System.out.println("1 - добавить задачу");
            System.out.println("2 - удалить первую задачу");
            System.out.println("3 - удалить задачу по номеру");
            System.out.println("4 - показать все задачи");
            System.out.println("5 - выход");
            System.out.print("Выберите пункт: ");

            String choice = scanner.nextLine();

            if (choice.equals("1")) {
                System.out.print("Введите текст задачи: ");
                String text = scanner.nextLine();
                tasks.add(text);
                System.out.println("Задача добавлена!");

            } else if (choice.equals("2")) {
                if (tasks.isEmpty()) {
                    System.out.println("Список пуст");
                } else {
                    tasks.remove(0);
                    System.out.println("Первая задача удалена.");
                }

            } else if (choice.equals("3")) {
                if (tasks.isEmpty()) {
                    System.out.println("Список пуст");
                } else {
                    System.out.print("Введите номер задачи: ");
                    try {
                        int num = Integer.parseInt(scanner.nextLine());
                        int index = num - 1;
                        if (index < 0 || index >= tasks.size()) {
                            System.out.println("Неверный номер");
                        } else {
                            tasks.remove(index);
                            System.out.println("Задача удалена.");
                        }
                    } catch (Exception e) {
                        System.out.println("Неверный номер");
                    }
                }

            } else if (choice.equals("4")) {
                if (tasks.isEmpty()) {
                    System.out.println("Список пуст");
                } else {
                    System.out.println("Список:");
                    for (int i = 0; i < tasks.size(); i++) {
                        System.out.println((i + 1) + ". " + tasks.get(i));
                    }
                }

            } else if (choice.equals("5")) {
                work = false;
                System.out.println("Выход из программы...");

            } else {
                System.out.println("Неверная команда");
            }
        }
        scanner.close();
    }
}
