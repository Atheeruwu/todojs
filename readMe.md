

```javascript
document.addEventListener('DOMContentLoaded', loadTodosFromStorage);
addButton.addEventListener('click', () => {
    if (!inputTodo.value.trim()) return;
    const newTodo = { text: inputTodo.value, id: Date.now() };
    createTodoElement(newTodo); saveTodoToStorage(newTodo); inputTodo.value = '';
});

todoList.addEventListener('click', (e) => {
    if (e.target.classList.contains('check-button')) e.target.closest('.itemall').classList.toggle('checklist');
    if (e.target.classList.contains('trash-button')) removeTodoFromStorage(e.target.closest('.itemall').dataset.id);
});

function saveTodoToStorage(todo) { const todos = JSON.parse(localStorage.getItem('todos')) || []; todos.push(todo); localStorage.setItem('todos', JSON.stringify(todos)); }
function loadTodosFromStorage() { (JSON.parse(localStorage.getItem('todos')) || []).forEach(createTodoElement); }
```

### Short Description:
1. **Event Listeners**: Waits for the DOM to load and adds click functionality for adding and interacting with todos.
2. **Adding Todo**: Adds new todo, saves it to `localStorage`, and clears the input.
3. **Loading Todos**: Loads and displays todos from `localStorage` when the page is refreshed.
4. **Check & Delete**: Toggles checkmark or deletes todo on button clicks.
5. **Saving Todos**: Saves the todo list to `localStorage` after each change.

![first one for todo](https://github.com/user-attachments/assets/af34ec1d-2301-4f14-96f9-2fbd7816e918)

![first two for todo](https://github.com/user-attachments/assets/0d2d5d33-fc90-4f80-86b6-089983596653)




