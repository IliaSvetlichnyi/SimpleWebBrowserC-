## SimpleWebBrowser Project using C#

### Introduction
SimpleWebBrowser is a custom-built, user-friendly web browser designed in C#. It incorporates key features like browsing history, favorites links, and a bulk download feature, offering a balanced and efficient browsing experience.

![Снимок экрана 26 12 2023 в 13 17 04](https://github.com/IliaSvetlichnyi/SimpleWebBrowserC-/assets/132441572/3a1b9608-b94e-412c-9ed2-dab87520aa97)



### Design Considerations
- **GUI Design**: Utilizes the GTK toolkit for robust interface design and modal dialogs for effective user interaction.
- **Data Structures**: Employs lists and key-value pairs for efficient tracking of browsing history and managing favorites.
- **Class Structure**: Organized into distinct classes for specific tasks, ensuring clarity and maintainability.

### User Guide
- **Navigation**: User-friendly URL entry bar with history-based suggestions.
- **Favorites**: Easy-to-use interface for adding, viewing, and managing favorite sites.
- **Bulk Download**: A feature to download multiple resources simultaneously with progress tracking.
- **History**: Accessible browsing history with chronological ordering and timestamps.

### Testing and Performance
- Multiple test cases covering core functionalities like URL navigation, error handling, and user interactions.
- Optimized for performance with efficient memory management and streamlined HTTP request processing.

### Developer Guide
**Application Design Overview:**

SimpleWebBrowser is meticulously crafted with a clear structure that ensures separation between various components of the application. This architectural choice is pivotal for maintaining distinct areas for visual elements (like buttons), stored data (such as favorites), and core functionalities (including webpage loading). Such separation is not only instrumental for troubleshooting but also streamlines the process of updates and enhancements.

**Architecture:**

The architecture of SimpleWebBrowser is inherently modular, divided into two primary folders: “Main Components” and “Controllers”.

- **Main Components**: This folder is the heart of the browser, containing files that are crucial for its primary functions.
  - `Program.cs`: Serves as the main entry point of the application.
  - `BrowserWindow.cs`: This file forms the graphical user interface of the browser, encompassing all UI elements ranging from navigation buttons to the address bar.
  - `HttpRequestManager.cs`: A utility class designed for managing HTTP requests, crucial for loading web pages.

- **Controllers**: Representing the logic layer of the application, this folder contains classes that implement various features of the web browser.
  - `HomePageManager.cs`: Manages the browser's homepage settings.
  - `FavoritesManager.cs`: Responsible for storing, retrieving, and managing user's favorite sites.
  - `HistoryManager.cs`: Tracks and stores browsing history.
  - `BrowserDialogs.cs`: A specialized class dedicated to managing dialog boxes, optimizing user interactions.
  - `BulkDownloader.cs`: Handles tasks related to the bulk downloading feature, allowing simultaneous downloading of multiple URLs.

**Code Fragments:**

1. **Application Flow (Program.cs):**
   ```csharp
   namespace SimpleWebBrowser
   {
       class Program
       {
           // Main entry point of the application.
           static void Main()
           {
               // Initialization procedures.
               Application.Init();

               // Instantiate main application window.
               var mainWindow = new MainAppWindow();

               // Display the main window.
               mainWindow.ShowAll();

               // Start the application loop.
               Application.Run();
           }
       }
   }
   ```
This code snippet provides a high-level overview of the application's main flow, from initialization to execution.

2. **Managing the Home Page (HomePageManager.cs):**
   ```csharp
   namespace SimpleWebBrowser.Controllers
   {
       public class HomePageManager
       {
           private string homePage = "http://defaultHomePage.com";

           // Property to get or set the home page URL
           public string HomePage
           {
               get => homePage;
               private set => homePage = value;
           }

           // Set the home page URL from a UI element
           public void SetHomePageFromUIElement(UIElement element)
           {
               homePage = element.TextValue;
           }

           // Load the current home page URL into a UI element
           public void LoadHomePageToUIElement(UIElement element)
           {
               element.TextValue = homePage;
           }

           // Attach home page related events to UI elements
           public void AttachHomePageEvents(...)
           {
               // Define actions for UI events related to home page functionalities.
           }
       }
   }
   ```
This excerpt illustrates the simplicity and functionality in managing the browser's home page, showcasing the ease of configuration and interaction.
   
### Installation & Execution
- **Prerequisites**: C#, .NET Framework, and GTK# for GUI development.
- **Deployment Steps**:
  1. Clone the repository.
  2. Build and compile the source files.
  3. Launch the application executable.

### Future Directions and Contributions
- Ongoing enhancements for user experience and integration of advanced web rendering engines.
- Contributions are welcome; please refer to the contribution guidelines for more information.
