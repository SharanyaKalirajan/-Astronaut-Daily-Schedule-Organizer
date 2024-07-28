import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        ScheduleManager scheduleManager = ScheduleManager.getInstance();
        TaskNotifier notifier = new TaskNotifier();
        User user = new User();
        notifier.subscribe(user);

        Scanner scanner = new Scanner(System.in);
        System.out.println("Astronaut Daily Schedule Organizer");

        while (true) {
            System.out.println("\nMenu:");
            System.out.println("1. Add Task");
            System.out.println("2. Remove Task");
            System.out.println("3. View Tasks");
            System.out.println("4. Exit");
            System.out.print("Choose an option: ");
            String choice = scanner.nextLine();

            switch (choice) {
                case "1":
                    System.out.print("Enter task description: ");
                    String description = scanner.nextLine();
                    System.out.print("Enter start time (HH:mm): ");
                    String startTime = scanner.nextLine();
                    System.out.print("Enter end time (HH:mm): ");
                    String endTime = scanner.nextLine();
                    System.out.print("Enter priority (High/Medium/Low): ");
                    String priority = scanner.nextLine();

                    Task task = TaskFactory.createTask(description, startTime, endTime, priority);
                    scheduleManager.addTask(task);
                    notifier.notifyObservers("Task '" + description + "' added from " + startTime + " to " + endTime + ".");
                    break;

                case "2":
                    System.out.print("Enter task description to remove: ");
                    description = scanner.nextLine();
                    scheduleManager.removeTask(description);
                    notifier.notifyObservers("Task '" + description + "' removed.");
                    break;

                case "3":
                    scheduleManager.viewTasks();
                    break;

                case "4":
                    scanner.close();
                    return;

                default:
                    System.out.println("Invalid option. Please try again.");
                    break;
            }
        }
    }
}
