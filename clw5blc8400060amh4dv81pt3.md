---
title: "A practical guide to using React Portals with confidence"
datePublished: Mon May 13 2024 18:51:23 GMT+0000 (Coordinated Universal Time)
cuid: clw5blc8400060amh4dv81pt3
slug: a-practical-guide-to-using-react-portals-with-confidence
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/xkBaqlcqeb4/upload/3ca5ed844d5428b60f5dfb2ac07bd324.jpeg
tags: javascript, reactjs, frontend-development, alexandrecalaca

---

---

## Brief overview

React Portals provide a powerful mechanism for rendering components outside the typical DOM hierarchy, offering developers a flexible approach to handling UI elements in unique ways.

Unlike traditional rendering, where components are confined to their parent's structure, portals enable the seamless integration of components across different parts of the document.

This allows developers to overcome common styling challenges and provides a clean solution to rendering elements in unconventional scenarios.

---

### **Importance of using Portals for certain scenarios**

Imagine you're working on a complex user interface that involves modals, tooltips, or other overlays. In these scenarios, React Portals shine by allowing you to render these elements outside their parent components.

This flexibility is crucial when dealing with CSS constraints or layout conflicts that might affect the visual presentation of your components. Portals provide an elegant solution to keep your UI clean, ensuring that certain elements can gracefully overlay without being constrained by the styles or structure of their parent components.

This flexibility not only enhances the aesthetics of your application but also contributes to a smoother and more intuitive user experience. React Portals can be a game-changer in achieving a polished and professional look.

---

## **Getting started with React Portals**

### Basic syntax and usage

Let's dive into the fundamental aspects of React Portals by exploring their basic syntax and usage. At its core, creating a portal is surprisingly straightforward.

In your React component, you encapsulate the content you want to portalize within a `createPortal` function. This function takes two arguments: the JSX content you wish to render, and the DOM node where you want to render it.

This abstraction allows you to maintain the React component structure while visually placing the content elsewhere in the DOM.

---

### Code snippet

```javascript
import React from 'react';
import ReactDOM from 'react-dom';

const MyPortalizedComponent = () => {
  const portalRoot = document.getElementById('portal-root');

  const portal = ReactDOM.createPortal(
    <div>This content is portaled!</div>,
    portalRoot
  );

  return portal;
};
```

Let's check a brief explanation:

```javascript
const portalRoot = document.getElementById('portal-root');
```

The previous code assumes that there is an HTML element with the id `portal-root` in your HTML file. This element will serve as the target container for the portalized content.

```javascript
const portal = ReactDOM.createPortal(
  <div>This content is portaled!</div>,
  portalRoot
);
```

The createPortal function takes two arguments: the `JSX content` you want to render, and the `DOM element` where you want to render it. In this case, it's rendering a simple with the text "This content is portaled!" into the portalRoot element.

---

### Setting up a Portal

Now, let's explore the steps to integrate a portal into your React application. First, you need to identify the target DOM node where your portalized content will be appended. This could be an existing element in your HTML, or you might create a new container specifically for portals.

Assuming you have a div with the id 'portal-root' in your HTML:

```javascript
<body>
  <div id="root"></div>
  <div id="portal-root"></div>
</body>
```

You can then create a portal as illustrated in the previous example. By calling `createPortal` and specifying the `target container`, you're instructing React to render the content within that specific DOM node.

---

## Real-world example

### Rendering Modals Outside Parent Components

```javascript
import React from 'react';
import ReactDOM from 'react-dom';

const Modal = ({ isOpen, onClose, children }) => {
  if (!isOpen) return null;

  const modalRoot = document.getElementById('modal-root');
  return ReactDOM.createPortal(
    <div className="modal-overlay" onClick={onClose}>
      <div className="modal-content" onClick={(e) => e.stopPropagation()}>
        {children}
      </div>
    </div>,
    modalRoot
  );
};

// In your App component or wherever you want to use the modal
const App = () => {
  const handleOpenModal = () => {
    // logic to open the modal
  };

  const handleCloseModal = () => {
    // logic to close the modal
  };

  return (
    <div>
      <button onClick={handleOpenModal}>Open Modal</button>
      <Modal isOpen={/* your state or logic for modal visibility */} onClose={handleCloseModal}>
        {/* Modal Content */}
        <p>This is modal content!</p>
      </Modal>
    </div>
  );
};
```

### Breaking it down

#### Modal component

```javascript
const Modal = ({ isOpen, onClose, children }) => {
  if (!isOpen) return null;
```

Here, `Modal` is a functional component, which takes three props: **isOpen** (boolean indicating whether the modal is open or not), **onClose** (function to handle modal closing), and children (the content to be displayed inside the modal).

The component checks if the `isOpen` prop is **false**. If it is, the component returns **null**, effectively not rendering anything. This allows for conditional rendering of the modal based on its open/closed state.

#### Portal setup

```javascript
const modalRoot = document.getElementById('modal-root');
  return ReactDOM.createPortal(
//Content
);
```

It finds the DOM element with the id `modal-root` (assumed to be present in the HTML), which will serve as the container for the portalized modal content.

It then uses `ReactDOM.createPortal` to create a portal, rendering the modal content into the specified `modalRoot`.

#### Modal Content

```javascript
<div className="modal-overlay" onClick={onClose}>
  <div className="modal-content" onClick={(e) => e.stopPropagation()}>
    {children}
  </div>
</div>,
```

The modal content consists of an overlay (`modal-overlay`) and the actual content container (`modal-content`).

The overlay has an onClick handler (onClose) to close the modal when clicking outside the content.

The content container prevents the click event from propagating up to the overlay, which prevents the modal from closing when clicking inside the modal content.

The `{children}` part renders the content passed as a child to the Modal component.

#### App component

```javascript
const App = () => {
  // Open and close modal logic here

  return (
    <div>
      <button onClick={handleOpenModal}>Open Modal</button>
      <Modal isOpen={/* your state or logic for modal visibility */} onClose={handleCloseModal}>
        {/* Modal Content */}
        <p>This is modal content!</p>
      </Modal>
    </div>
  );
};
```

The `App` component demonstrates how to use the `Modal` component. It has a button to open the modal and passes the modal's open/close logic as props to the `Modal` component.

---

## Pros and cons of React Portals

### Advantages

React Portals offer several compelling advantages that contribute to a more flexible and maintainable codebase. One key benefit is the ability to escape the constraints of a parent component's DOM hierarchy.

This proves invaluable when dealing with UI elements like modals or tooltips, where rendering outside the usual flow of components enhances the overall user experience.

Portals also facilitate cleaner code organization by allowing developers to keep the modal logic separate from the main component, promoting better code readability and maintainability.

---

### Potential challenges

While React Portals offer a robust solution, it's crucial to consider potential challenges. Developers should exercise caution when relying heavily on portals for components that require complex interactivity or depend on specific DOM structures.

Managing state and events between portalized and non-portalized components may introduce subtle complexities.

Additionally, portals could potentially impact accessibility, and it's important to ensure that the user experience remains seamless for all users, including those with disabilities.

---

### Trade-offs

The decision to use React Portals involves a trade-off between the advantages they offer and the potential challenges they introduce. In scenarios where maintaining a clean UI hierarchy and avoiding styling conflicts is critical, portals can be a powerful tool. However, developers should assess the specific needs of their application and carefully consider whether the complexity introduced by portals is justified.

Balancing trade-offs also extends to the project's long-term maintainability. While portals can enhance certain aspects of development, overreliance may lead to codebases that are harder to understand for future developers. Striking the right balance involves thoughtful consideration of the specific use case, the complexity of the application, and the long-term goals of the development team.

---

## Best practices

### **Tips for Optimizing Portal Usage**

When leveraging React Portals, optimizing their usage is key to ensuring a smooth and efficient application. Consider implementing lazy loading for portal components to enhance initial load times.

This way, resources are fetched only when the portal is triggered, minimizing unnecessary overhead.

Additionally, be mindful of the frequency of re-renders, especially when dealing with dynamic content. Optimize performance by strategically updating the portal content only when necessary, avoiding unnecessary renders for improved efficiency.

---

### **Addressing Common Pitfalls**

While React Portals offer a powerful solution, they come with their share of potential pitfalls. One common challenge is handling state and events between portalized and non-portalized components.

To address this, establish a clear communication strategy. Utilize context or a state management library to facilitate seamless interaction between components, ensuring that updates and events are appropriately propagated.

Another pitfall involves potential accessibility issues, particularly when portalized content is not properly managed. Test and implement accessibility features to guarantee a consistent and inclusive user experience.

Another consideration is handling unmounting scenarios. When a component inside a portal is unmounted, ensure proper cleanup to prevent memory leaks or unexpected behavior.

Incorporate lifecycle methods or useEffect hooks to manage component unmounting effectively. Lastly, be cautious with the use of global styles in portalized content, as they might conflict with the styles of the main application. Utilize encapsulated styles or scoped styling solutions to maintain a cohesive design.

---

### **Ensuring Maintainability and Code Cleanliness:**

To ensure the maintainability and cleanliness of your codebase, adhere to consistent coding conventions and patterns. Clearly document the usage of portals in your application, providing insights into why and where portals are employed.

Consider encapsulating portal logic into reusable components or hooks, promoting a modular and organized code structure.

Adopt a naming convention that clearly distinguishes portal components, making it easier for developers to identify and understand their purpose.

---

## Conclusion

In conclusion, React Portals offer a versatile toolset to elevate your application's visual appeal and user experience.

By understanding their advantages, considering potential challenges, and adopting best practices, you're well-equipped to leverage React Portals with confidence.

So, go ahead, experiment, and unlock the full potential of React Portals in your UI development journey.

---

## **Done**

---

## **Celebrate**

![The It Crowd Birthday GIFs | Tenor](https://media.tenor.com/kDyYq4PQuIgAAAAC/clapping-it-crowd.gif align="left")

---

## **Reach me out**

* [**Github**](https://github.com/alexcalaca)
    
* [**Linke**](https://linkedin.com/in/alexandrecalacaofficial)[**dIn**](https://github.com/alexcalaca)
    
* [**H**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**ashnode**](https://linkedin.com/in/alexandrecalacaofficial)
    
* [**You**](https://github.com/alexcalaca)[**t**](https://hashnode.com/onboard?next=/@alexandrecalaca)[**u**](https://www.youtube.com/@alexandrecalacaofficial)[**be**](https://linkedin.com/in/alexandrecalacaofficial)
    

---

## Final thoughts

Thank you for reading this article.

If you have any questions, thou[g](https://github.com/alexcalaca)hts, suggestions, or corrections, please share them with us.

We appreciate your feedback and look forward to hearing from you.

Feel free to suggest topics for future blog articles. Until next time!