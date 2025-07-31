# -E-Commerce-Order-Processing-Java-program
Calculate the total price of all orders placed on a specific date.
       import java.util.ArrayList;
      import java.util.List;



    class Order {
    int id;
    String item;
    double price;
    String date;

    public Order(int id, String item, double price, String date) {
        this.id = id;
        this.item = item;
        this.price = price;
        this.date = date;
    }

    // Getter for price
    public double getPrice() {
        return price;
    }

    // Getter for date
    public String getDate() {
        return date;
    }
    }

    public class OrderProcessor {
    // 🧮 Procedural function to calculate total price on a given date
    public static double calculateTotalPrice(List<Order> orders, String targetDate) {
        double total = 0.0;
        for (Order order : orders) {
            if (order.getDate().equals(targetDate)) {
                total += order.getPrice();
            }
        }
        return total;
    }

    public static void main(String[] args) {
        // 📦 Sample data (could be from DB or file)
        List<Order> orders = new ArrayList<>();
        orders.add(new Order(1, "Laptop", 999.99, "2025-07-31"));
        orders.add(new Order(2, "Keyboard", 49.99, "2025-07-31"));
        orders.add(new Order(3, "Mouse", 25.99, "2025-07-30"));
        orders.add(new Order(4, "Monitor", 199.99, "2025-07-31"));

        String today = "2025-07-31";

        // 🖨️ Call the function (procedural style) with OOP objects
        double total = calculateTotalPrice(orders, today);
        System.out.printf("Total value of orders on %s is ₹%.2f%n", today, total);
    }
}
