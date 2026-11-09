# Exp 8 – React User Interactions: onChange and onSubmit

## NAME: AMMINENI MOKSHA SREE  
## REG NO: 2305001001 

## Aim
To develop a React application using `onChange` and `onSubmit` events to handle user input and form submission.

## Objectives
- Understand the `onChange` event in React.
- Understand the `onSubmit` event in React.
- Use `useState` to store form data.
- Handle multiple input fields using a single state object.
- Process form data when the user submits the form.

## Program

### Step 1: Create a React Project

```bash
npm create vite@latest react-interactions
cd react-interactions
npm install
npm run dev
```

Select React as the framework and JavaScript as the variant.

### Step 2: App.jsx

```jsx
import { useState } from "react";
import "./App.css";

function App() {
  const [formData, setFormData] = useState({
    name: "",
    email: ""
  });

  const handleChange = (event) => {
    const { name, value } = event.target;

    setFormData({
      ...formData,
      [name]: value
    });
  };

  const handleSubmit = (event) => {
    event.preventDefault();

    alert(
      "Name: " + formData.name +
      "\nEmail: " + formData.email
    );
  };

  return (
    <div className="container">
      <h1>Registration Form</h1>

      <form onSubmit={handleSubmit}>
        <label>Name:</label>
        <input
          type="text"
          name="name"
          value={formData.name}
          onChange={handleChange}
          placeholder="Enter your name"
          required
        />

        <label>Email:</label>
        <input
          type="email"
          name="email"
          value={formData.email}
          onChange={handleChange}
          placeholder="Enter your email"
          required
        />

        <button type="submit">Submit</button>
      </form>
    </div>
  );
}

export default App;
```

### Step 3: App.css

```css
.container {
  width: 350px;
  margin: 50px auto;
  padding: 25px;
  border: 1px solid gray;
  border-radius: 10px;
}

h1 {
  text-align: center;
  color: blue;
}

label {
  display: block;
  margin-top: 15px;
  font-weight: bold;
}

input {
  width: 100%;
  padding: 10px;
  margin-top: 5px;
  box-sizing: border-box;
}

button {
  margin-top: 20px;
  padding: 10px 20px;
  background-color: blue;
  color: white;
  border: none;
  cursor: pointer;
}
```

## Output

<img width="1090" height="570" alt="image" src="https://github.com/user-attachments/assets/042a8e82-7d7a-4fd5-a7cd-57bbfb94001b" />

## Result

Thus, a React application was successfully developed using `onChange` and `onSubmit` events to capture user input, update state, and handle form submission.
