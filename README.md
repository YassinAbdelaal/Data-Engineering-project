# Inventory Management System (IMS)

## Project Scope

The **Inventory Management System (IMS)** is a robust web-based application tailored for businesses particularly in the **automotive repair industry** to manage their inventory operations across multiple branches. Its core functionality includes monitoring stock levels, managing product data, recording sales, and generating reports.

The IMS addresses the common challenges faced by inventory managers and administrators by leveraging a relational database and an intuitive web interface. It streamlines inventory-related workflows, reduces manual effort, and enhances operational efficiency.

Key benefits include:

* Improved accuracy and reliability of inventory records
* Real-time stock tracking across multiple locations
* Automated alerts to prevent overstocking and understocking
* Enhanced customer service through optimized stock levels

With flexible configuration options, the IMS supports customized inventory policies and reporting needs, enabling **data-driven decision-making** and **supply chain optimization**.

## Tools

* **Programming Language**: C# within the .NET ecosystem, providing a robust and type-safe environment for building scalable and maintainable application logic.
* **Framework**: .NET enabling high performance, cross-platform compatibility, and support for modern web applications.
* **Database**: SQL Server, used for efficient data storage, retrieval, and management, ensuring reliable and secure handling of inventory data with support for complex queries and transactions.
* **ORM (Optional)**: Entity Framework Core, integrated with .NET C# to simplify database interactions, improve development speed, and ensure type-safe data operations.
* **Frontend Web Framework**: ASP.NET Core MVC, used for the frontend to implement a Model-View-Controller architecture, enabling the development of dynamic, scalable, and maintainable web interfaces with clear separation of concerns.
* **Frontend Markup and Styling**:

  * **HTML**: Utilized as the standard markup language for structuring the frontend web interfaces, ensuring semantic and accessible content delivery within ASP.NET Core MVC views.
  * **CSS**: Employed for custom styling and layout adjustments, complementing Bootstrap to fine-tune the visual design and ensure a cohesive user experience.
  * **Bootstrap**: Used as the primary frontend CSS framework to provide responsive, mobile-first styling, ensuring user-friendly, visually consistent, and cross-device-compatible web interfaces with minimal custom CSS.
* **Web Server**: Microsoft Internet Information Services (IIS), selected to host the ASP.NET Core MVC application, offering robust performance, security features, and seamless integration with the .NET ecosystem for reliable deployment.
* **Authentication/Authorization**: ASP.NET Core Identity, paired with SQL Server, to implement secure user management and role-based access control.

## Database Design

**Decision**: Use SQL Server with a normalized schema comprising the following tables:

### Products Table

Stores product details:

* `ProductID` \[PK]
* `Name`
* `Type`
* `Color`
* 'Price'
* 'Code'
* 'CategoryID'

### Inventory Table

Tracks stock levels:

* `InventoryID` \[PK]
* `ProductID` \[FK]
* `LocationID` \[FK]
* `Quantity`
* `Shelf`
* `Location`
* 'Product'
### Locations Table

Manages warehouse/store locations:

* `LocationID` \[PK]
* `LocationName`
* `Address`

### Orders Table

Records inter-location transfers:

* `OrderID` \[PK]
* `SourceLocationID` \[FK]
* `DestinationLocationID` \[FK]
* `OrderDate`
* `Status`

### OrderDetails Table

Details products in orders:

* `OrderDetailID` \[PK]
* `OrderID` \[FK]
* `ProductID` \[FK]
* `Quantity`
* 'Prodcut'

### Sales Table

Logs sales transactions:

* `SaleID` \[PK]
* `EmployeeID` \[FK]
* `ClientID` \[FK]
* `SaleDate`
* `WindshieldCode` \[nullable]
* `AdhesiveAmount` \[nullable]

### SaleDetails Table

Specifies products sold:

* `SaleDetailID` \[PK]
* `SaleID` \[FK]
* `ProductID` \[FK]
* `Quantity`

### Clients Table

Stores client information:

* `ClientID` \[PK]
* `Name`
* `Phone`
* `car_number`
* `Address`

### Employees Table

Manages employee data:

* `EmployeeID` \[PK]
* `Name`
* `Username`
* `PasswordHash`
* `Role`
* * `Phone`
* `LocationID` \[FK]
* * `isactive'
### StockRequest Table

Handles stock transfer requests between locations:

- `RequestId` [PK]
- `FromLocationId` [FK] 
- `ToLocationId` [FK]  
- `ProductCode` [FK]  `
- `Quantity`
- `RequestDate'
- `Status`

### GlassFixationCategory Table

Stores categories for glass fixation with associated costs:

- `id` [PK]
- `CatName`
- `fixation_cost`
- `Products`


## 🚀 Build & Run Instructions

### 🖥️ Option 1: Using Visual Studio (Recommended)

1. **Install Visual Studio 2022 or later**

   * During installation, select:

     * ".NET desktop development"
     * ".NET and web development"

2. **Clone the repository**:

   ```bash
   git clone https://github.com/Abdelrahman2610/Inventory-Management-System.git
   cd Inventory-Management-System
   ```

3. **Switch to the **\`\`** branch**:

   ```bash
   git checkout master
   ```

4. **Open the **\`\`** file** in Visual Studio.

5. **Open the terminal in Visual Studio**:

   * Go to **View → Terminal** or press `Ctrl + ` (backtick)

6. **Run the following commands** in the terminal:

   ```bash
   dotnet restore
   dotnet build
   dotnet run
   ```

7. **The application should launch** in your browser if it's an ASP.NET Core MVC app.

---

### 💻 Option 2: Using VS Code + .NET CLI

1. **Install prerequisites**:

   * [.NET SDK 6.0+](https://dotnet.microsoft.com/download)
   * [Visual Studio](https://code.visualstudio.com/)
   * [C# Extension (by Microsoft)](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)
   * [SQL Server Management Studio (SSMS)](https://learn.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms)


2. **Clone the repository**:

   ```bash
   git clone https://github.com/Abdelrahman2610/Inventory-Management-System.git
   cd Inventory-Management-System
   ```

3. **Switch to the **\`\`** branch**:

   ```bash
   git checkout master
   ```


4. **Restore dependencies**:

   ```bash
   dotnet restore
   ```

5. **Build the project**:

   ```bash
   dotnet build
   ```

6. **Run the application**:

   ```bash
   dotnet run
   ```

---

### ✅ Requirements Summary

* **.NET SDK 6.0 or higher**
* **Visual Studio 2022 or later** with workloads:

  * .NET desktop development
  * ASP.NET and web development
* Or **Visual Studio Code** with:

  * .NET SDK installed
  * C# Extension for VS Code
* **Git** installed to clone the repository
* Ensure to **checkout to the **\`\`** branch** before running the application.
