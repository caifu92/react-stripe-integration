<h1 align="center">REACT STRIPE INTEGRATION</h1>

<div align="center">

All those libraries put together in a nice interface easy to use and implement.

</div>

## Installation
clone repository

## Usage

### Change Icons
You can change the icons in [/src/Components/Views/StepperIcons.js](/src/Components/Views/StepperIcons.js). You'll find the list of icons available at [Material-UI](https://material-ui.com/components/material-icons/).

### Add ore Remove steps
To adjust the number of steps go to [/src/Components/Views/Stepper.js](/src/Components/Views/Stepper.js). There you'll find a function call ```StepContent``` with the list of Forms being used:

This application uses [React Hooks](https://reactjs.org/docs/hooks-intro.html), including useContext to keep track of the data entered in the form.

Therefore if you modify the fields you'll have to adjust the initial state in the reducer available at [/src/Components/StateContext/reducer.js](/src/Components/StateContext/reducer.js)

### Setup Stripe

You simply need to save your Stripe keys in [/public/keys.php](/public/keys.php).

In that example will only enable credit card payments but you can of course other type of payments by either editing the [payment form](/src/Components/Views/Forms/PaymentForm.js) or adding a form by following the step above.

```jsx
const StepContent = ({ step }) => {
    switch (step) {
        case 0:
            return <ContactForm />;
        case 1:
            return <ServiceForm />;
        case 2:
            return <PaymentForm />;
        default:
            return <></>;
    }
}
```

Make sure to adjust the loop in the ```Stepper``` function as well:

```jsx
//Change the number of loops by adjusting the array here
{[1, 2, 3].map(e => (
    <Step key={e}>
        <StepLabel StepIconComponent={StepperIcons} />
    </Step>
))}
```
### Change the theme

To change the theme color, font, etc. go to [/src/Components/constants/theme.js](/src/Components/constants/theme.js)

## Questions

For *how-to* questions and other non-issues,
please use [StackOverflow](https://stackoverflow.com/questions/tagged/material-ui) instead of Github issues or contact me personaly via my [website](https://angeloron.com/contact).

## License

This project is licensed under the terms of the
[MIT license](/LICENSE).
