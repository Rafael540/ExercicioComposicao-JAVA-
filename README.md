# ExercicioComposicao-JAVA-
Exercicio de composicação em JAVA.

````
classDiagram
    Order --> OrderItem : items
    Order --> Client : client
    OrderItem --> Product : product
    OrderStatus : <<enum>>
    OrderStatus : PENDING_PAYMENT = 0
    OrderStatus : PROCESSING = 1
    OrderStatus : SHIPPED = 2
    OrderStatus : DELIVERED = 3

    class Order {
        - moment : Date
        - status : OrderStatus
        + addItem(item : OrderItem) : void
        + removeItem(item : OrderItem) : void
        + total() : Double
    }

    class Client {
        - name : String
        - email : String
        - birthDate : Date
    }

    class OrderItem {
        - quantity : Integer
        - price : Double
        + subTotal() : Double
    }

    class Product {
        - name : String
        - price : Double
    }
