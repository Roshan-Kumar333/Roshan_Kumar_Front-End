# Roshan_Kumar_Front-End
## 1 Explain what the simple List component does.

The **List** component is a React component that takes an array of items as a prop and renders a list of these items. It does this by mapping over the **items** array and rendering a **SingleListItem** component for each item.

The **SingleListItem** component is a small component that has four props: **index**, **isSelected**, **onClickHandler**, and **text**. When rendered, it displays an **li** element with the **text** content of the text prop, and sets the background color of the **li** element based on whether the **isSelected** prop is true or false. Additionally, it adds an **onClick** event listener to the **li** element. When the element is clicked, the **onClickHandler** prop function is invoked, passing the **index** prop as an argument.

The **List** component uses the **useState** hook to keep track of the currently selected item. When the **items** prop changes, the **useEffect** hook is used to reset the selected item to **null**. The **handleClick** function updates the selected item by setting the **selectedIndex** state to the index of the clicked item.

 ## 2 What problems / warnings are there with code?
I encountered following problems/warnings while going through the given code.

a. In the **Single List Item Component**, the **onClickHandler** Function will be invoked immediately as soon as the app gets rendered

`onClick={onClickHandler(index)}`

Instead of this we should assign a callback function to the **onClick** event such that the **onClickHandler** function will be invoked only when the corresponding event occurs like shown below

`onClick={() => onClickHandler(index)}`
