# Task App

This is a simple Task App that allows users to add tasks to a list. The app consists of an input field for entering a task name and a table where all added tasks are displayed.

## Features

- Add tasks via an input form.
- Display tasks in a table format.

## How it Works

1. The app includes an input field where users can type in a task.
2. When the "Add Task" button is clicked, the task is added to a table below the form.
3. The tasks are displayed in a table row (`<tr>`) under the `Task Name` column.

## Code Breakdown

### HTML Structure

- The HTML file is structured with a simple form and a table:
  - The form contains an input field where users enter tasks.
  - The table displays the list of tasks, with a `<thead>` for the table header and a `<tbody>` (with the ID `tasks`) where new tasks are appended.

```html
<form>
  <input type="text" name="task" id="task-input">
  <button type="submit">Add Task</button>
</form>
```

### JavaScript Functionality

- The JavaScript listens for a form submission using the `submit` event.
- When the form is submitted:
  - The default behavior is prevented using `e.preventDefault()`.
  - The task from the input field is retrieved.
  - A new table row (`<tr>`) is created with the task inside a table cell (`<td>`).
  - This new task row is appended to the `tbody` element in the table.

```javascript
document.querySelector('form').addEventListener('submit', function(e) {
  e.preventDefault();
  var task = document.querySelector('#task-input').value;
  var tasks = document.querySelector('#tasks');
  var newTask = document.createElement('tr');
  newTask.innerHTML = '<td>' + task + '</td>';
  tasks.appendChild(newTask);
});
```

## How to Run

1. Open the HTML file in any modern web browser.
2. Enter a task in the input field and click the "Add Task" button.
3. The task will appear in the table below.

## Technologies Used

- HTML5
- JavaScript

## Potential Improvements

- Add task removal functionality.
- Implement task completion status (e.g., checkboxes).
- Style the application using CSS for better user experience.

## License

This project is open-source and free to use.
