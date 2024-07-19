# Interactive Book Store Application

https://elegant-dasik-4e6857.netlify.app

The Interactive Book Store Application is a comprehensive web platform designed to offer a seamless and engaging book shopping experience. Developed using ReactJS, this application leverages modern web technologies to provide robust functionality and a user-friendly interface. The project is organized with a clear structure and follows clean code guidelines to ensure maintainability and scalability. The application features multiple pages, including Home, Book List, Book Details, Cart, and Checkout, each tailored to enhance the user experience.

On the Home page, users are greeted with a welcoming header that includes links to various sections of the application, along with a banner that encourages them to explore the collection of books. The Book List page is meticulously designed to display a wide array of books, each presented with its image, title, subtitle, and price. Users can easily search for specific books by title or author, and filter the list by price range using a convenient range slider. This page is integrated with the IT Bookstore API to fetch real-time data, ensuring that users have access to the latest book information.

When a user selects a book, they are directed to the Book Details page, which provides comprehensive information about the chosen book, including an image, title, subtitle, price, and a detailed description. Users have the option to add the book to their cart directly from this page. The Cart page then displays all the selected items, allowing users to review their choices, remove any items if necessary, and proceed to checkout. An order summary provides a clear overview of the items and their total cost.

The Checkout page is designed to gather personal details required for the order, such as first name, last name, email, and mobile number. Users can review their order summary one last time before placing their order. Navigation throughout the application is intuitive, with back buttons available on every page to enhance usability.

State management is efficiently handled using Redux or React Context, ensuring that the cart's state is consistently maintained across different components and routes. The application also integrates several third-party packages to enhance functionality, such as react-loader-spinner for loading animations, react-icons for a variety of icons, rc-slider for the range slider, and rc-tooltip for tooltips. React Router (v5.2.0) is utilized for effective navigation between pages.

To ensure a smooth development experience, the project adheres to GitHub guidelines with frequent commits and concise, specific commit messages. A README file provides detailed instructions on setting up and using the project, making it accessible for other developers. The application's codebase is well-organized, following the create-react-app folder structure, and all errors are handled gracefully to prevent any disruption to the user experience.

Future improvements for the application include implementing user authentication to personalize the shopping experience and ensure secure access to user data. This feature would enhance the application's functionality by allowing users to create accounts, save their preferences, and view their order history. Overall, the Interactive Book Store Application stands as a testament to modern web development practices, offering a rich feature set, responsive design, and a pleasant user experience.

provide 5 lines summary
ChatGPT
The Interactive Book Store Application is a ReactJS-based platform allowing users to browse, search, and purchase books seamlessly. It features pages for Home, Book List, Book Details, Cart, and Checkout, with intuitive navigation and real-time data integration via the IT Bookstore API. State management is handled with Redux or React Context, ensuring consistent cart functionality. Third-party packages enhance features like loading animations and tooltips. Future improvements include implementing user authentication for a personalized shopping experience.



https://github.com/user-attachments/assets/1d2402f0-5bfb-4925-9847-7b525f99da4e



> Demo

### Usage

```
git clone <github repository link>  //to clone the github repository
npm install                         //to install all the dependencies required to run application
npm start                           //to start the application
```

**Note:** Node should be greater than or equal to **14.0** to run the Application.

## Development

### Tech Stack

Frontend - ReactJS (React Router, Redux/React Context)

### Functionality

| Page         | Page Details                                                                                                                             | Navigation                                                                             |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| Home         | Header - Links for pages Home, Book List, Cart, Banner - Heading, description, and “Explore Books” Button                                | -                                                                                      |
| Book List    | Header - Links for pages Home, Book List, Cart, Book Items - image, title, subtitle, price, Search (by title, author), Filter (by price) | “Book List” link in Header, “Explore Books” Button, “Back” Button in Book Details Page |
| Book Details | Book detailed Information - image, title, subtitle, price, description, etc., “Add to cart” Button, “Back” button                        | Each Book Item in Book List Page                                                       |
| Cart         | Cart Items, “Remove” Button, Order Summary, “Checkout” Button                                                                            | “Cart” link in Header, “Back” Button in Checkout Page                                  |
| Checkout     | “Back” Button, Order Form - Personal Details - First Name, Last Name, Email, Mobile No. , Place Order Button, Order Summary              | “Checkout” Button in Cart                                                              |

### Technical Details

### Routes

| Page         | Route        | Path       |
| ------------ | ------------ | ---------- |
| Home         | Home         | /          |
| Book List    | Book List    | /books     |
| Book Details | Book Details | /books/:id |
| Cart         | Cart         | /cart      |
| Checkout     | Checkout     | /checkout  |
| Not Found    | Not Found    | /not-found |

### Routes & Components

**Home**

| Component | Details                                         | State               | API (IT Bookstore) |
| --------- | ----------------------------------------------- | -----               | ------------------ |
| Home      | Heading, Description, and "ExploreBooks" button | -                   | -                  |
| Header    | Links for pages Home, Book List, Cart           | (Context Consumer)  | -                  |

**Book List**

| Component    | Details                                    | State                                 | API (IT Bookstore) |
| ------------ | ------------------------------------------ | ------------------------------------- | ------------------ |
| BookList     |                                            | apiStatus, booksData, priceRangeValue | /new               |
| Header       | Links for pages Home, Book List, Cart      | (Context Consumer)                    | -                  |
| SearchInput  | Search (by title, author)                  | searchInputValue                      | /search/{query}    |
| PriceRange   | Filter (by price)                          | -                                     | -                  |
| BookItem     | Book Items (title, subtitle, image, price) | -                                     | -                  |
| Loader       |                                            | -                                     | -                  |
| ErrorMessage |                                            | -                                     | -                  |

**Book Details**

| Component    | Details                                                                                                            | State                      | API (IT Bookstore) |
| ------------ | ------------------------------------------------------------------------------------------------------------------ | -------------------------- | ------------------ |
| BookDetails  | Book detailed Information -  image, title, subtitle, price, description, etc., “Add to cart” Button, “Back” button | apiStatus, bookDetailsData | /books/{isbn}      |
| Header       | Links for pages Home, Book List, Cart                                                                              | (Context Consumer)         | -                  |
| Loader       |                                                                                                                    | -                          | -                  |
| ErrorMessage |                                                                                                                    | -                          | -                  |

**Cart**

| Components | Details                                                         | State              | API (IT Bookstore) |
| ---------- | --------------------------------------------------------------- | ------------------ | ------------------ |
| Cart       | Cart Items, “Remove” Button, Order Summary, “Checkout” Button   | (Context Consumer) | -                  |
| Header     | Links for pages Home, Book List, Cart                           | (Context Consumer) | -                  |
| CartItem   | Book Detailed Info (image, title, subtitle, price, description) | (Context Consumer) | -                  |

**Checkout**

| Components      | Details                                                                                                      | State                        | API (IT Bookstore) |
| --------------- | ------------------------------------------------------------------------------------------------------------ | ---------------------------- | ------------------ |
| Checkout        | “Back” button                                                                                                | (Context Consumer)           | -                  |
| UserDetailsForm | Order Form - Personal Details - First Name, Last Name, Email, Mobile No. , Place Order Button, Order Summary | userDetails, isFormSubmitted | -                  |

**Not Found**

| Components | Details                               | State              | API (IT Bookstore)                    |
| ---------- | ------------------------------------- | ------             | ------------------------------------- |
| NotFound   | -                                     | -                  | -                                     |
| Header     | Links for pages Home, Book List, Cart | (Context Consumer) | Links for pages Home, Book List, Cart |

**App**

| Component | Details | State                                                                     | API (IT Bookstore) |
| --------- | ------- | ------------------------------------------------------------------------- | ------------------ |
| App       | -       | cartList (Context Provider), Context: cartList, addToCart, deleteFromCart | -                  |

### Guidelines

- Followed Github Guidelines
  - Made the commits often and made sure the commit messages are concise and specific
  - Included a README file for explaining the project setup, usage instructions, and any additional information.
- Followed Clean Code Guidelines
- The repo is well-organized and easy to navigate
  - Followed the `create-react-app` folder structure
- The Application handled all the errors

### Resources

#### Design Files

Pages: Home, Book List, Book Details, Shopping Cart, Checkout 

Reference: https://www.crossword.in/

#### API

Books, Book Details, Search

Reference: https://api.itbook.store

#### Third-party packages

- Loader (react-loader-spinner)
- Icons (react-icons)
- Range Slider (rc-slider) 
- React Tooltip (rc-tooltip) for tooltips in Range slider
- React Router (react-router-dom v5.2.0)

### Future Improvements

- Implement User Authentication
