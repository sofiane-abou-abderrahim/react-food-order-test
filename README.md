# Time To Practice: Food Order App

## Components, State, Context, Effects, HTTP Requests & More!

- Building a Complete Project From the Ground Up
- Building & Configuring Components
- Using State & Context
- Managing HTTP Requests & Side Effects

# A Challenge For You

## Build a "Food Order" web app

- Use the starting project attached to this lecture
- Add components for displaying products, the cart (in a modal) and a checkout form (also in a modal)
- Fetch the (dummy) meals data from the backend & show it on the screen (Get /meals)
- Allow users to add & remove products to / from the cart
- Send cart data along with user data (full name, email, street, postal code, city) to the backend (POST /orders)
- Handle loading & error states

# Steps

## 0. Starting Project

1. run `npm install` in the `backend` folder
2. run `npm install` in the main project folder (frontend)
3. run `npm start` in the `backend` folder
4. run `npm run dev` in the main project folder (frontend)
5. create a `README.md` file

## 1. Planning the App & Adding a First Component

1. add a `components` folder
2. inside of it, add a `Header.jsx` file
3. use this header in the `App.jsx` component

## 2. Fetching Meals Data (GET HTTP Request)

1. add a new `Meals.jsx` component
2. send a GET HTTP request to the dummy backend from inside `Meals.jsx`
3. output the meals items (just the names for now) from inside `App.jsx`

## 3. Adding a "MealItem" Component

1. add a `MealItem.jsx` file
2. output the `<MealItem>` component in `Meals.jsx`
3. prepend the image source data in `MealItem.jsx` to load the images from the backend

## 4. Formatting & Outputting Numbers as Currency

1. add a new `util` folder & add a new `formatting.js` file inside it for formatting the price
2. use the `currencyFormatter` function in `MealItem.jsx`

## 5. Creating a Configurable & Flexible Custom Button Component

1. add a `UI` subfolder inside the `components` folder for UI core generic building blocks
2. add a new `Button.jsx` inside that `UI` folder
3. use this `<Button>` component in your app, for example:
   1. a text only button style in the `Header.jsx`component
   2. an other button style in the `MealItem.jsx` component

## 6. Getting Started with Cart Context & Reducer

1. use React's context feature to manage the cart data in a more general centralized way
   1. add a `store` folder
   2. inside it, add a `CartContext.jsx` file where you manage this cart data & this cart context
2. use React's Reducer feature instead of State

## 7. Finishing & Using the Cart Context & Reducer

1. finish the cart logic inside the `cartReducer` function in `CartContext.jsx`
2. connect the cart logic with help of `useContext()` to the different components
   1. use the `useReducer()` hook correctly inside of the `CartContextProvider` component
   2. pass the cart context value to the `<CartContext.Provider>` component
3. use the cart context inside of the other components
   1. wrap all your components with the `<CartContextProvider>` component in `App.jsx`
   2. use the cart context in `MealItem.jsx` to update your cart
   3. access the cart context in `Header.jsx` to display the number of meals in the cart

## 8. Adding a Reusable Modal Component with useEffect

1. build a modal as a standalone reusable UI component named `Modal.jsx`
2. use an `open` prop & `useEffect()` & `useRef()` to open this dialog

## 9. Opening the Cart in the Modal via a New Context

1. add a new `Cart.jsx` component for outputting the cart data on the screen
2. use `useContext()` to get access to the cart items stored in the cart context
3. add a new `UserProgressContext.jsx` component for taking care of showing or not showing this cart data
4. use the `UserProgressContextProvider` in `App.jsx` and wrap it around the other components
5. use the `UserProgressCtx` in `Header.jsx`
6. show the Cart component in `Cart.jsx` with help of `useContext()`
7. output the `<Cart>` component in `App.jsx`
8. set the logic for closing the modal in `Cart.jsx` & `Modal.jsx`

## 10. Working on the Cart Items

1. add a new `CartItem.jsx`
2. output the `<CartItem>` component in `Cart.jsx`
3. make sure the buttons increase & decrease the items quantity in the cart

## 11. Adding a Custom Input Component & Managing Modal Visibility

1. show the `Go to Checkout` button only if we have an item in the cart in `Cart.jsx`
2. add a new `Checkout.jsx` component that will show a new page when clicking on the `Go to Checkout` button
3. it should open a modal
4. create a new shared `Input.jsx` component
5. manage opening & closing the modal
6. output the `<Checkout>` component in `App.jsx` to show the checkout modal
7. update the `UserProgress` context whenever the dialog is closed with `escape` by adding an `onClose` prop in `Modal.jsx`
8. use the `onClose` prop in `Cart.jsx` & `Checkout.jsx`

## 12. Handling Form Submission & Validation

1. handle form submission in `Checkout.jsx`
2. validate the input in `Input.jsx` with help of the `required` attribute
3. get hold of the entered values with the built-in `FormData` feature in `Checkout.jsx`

## 13. Sending a POST Request with Order Data

1. send the POST request inside the `handleSubmit` function in `Checkout.jsx`
2. make some order on the app & check the `orders.json` file to see whether the order was sent successfully

## 14. Adding a Custom HTTP Hook & Avoiding Common Errors

1. create a new `hooks` folder & add a new `useHttp.js` file inside of it
2. define a new `sendHttpRequest` helper function
3. define another new `sendRequest` function inside of the `useHttp` custom hook function
4. use `try / catch`
5. manage some state to reflect those different requests states in the UI
6. use the `useHttp` custom hook in `Meals.jsx`

## 15. Handling HTTP Loading & Error States

1. add a new `Error.jsx` component to output some error message
2. add CSS styles for loading & error messages in `index.css`

## 16. Finishing Touches

1. use the `useHttp.jsx` hook component in `Checkout.jsx`
2. handle the `data`, `isLoading` & `error` states
3. clear the cart once submitted the order in `Checkout.jsx` with help of a new `clearCart` function defined in `CartContext.jsx`
4. clear the data after submitted a successful order with help of a new `clearData` function in `useHttp.js` & call it in `Checkout.jsx`
