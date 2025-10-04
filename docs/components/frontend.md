# Frontend Assets

## `styles.css`
Mobile-first CSS with Bootstrap-compatible classes and custom variables. Enhances visuals for navbar, hero, cards, and forms.

## `script.js`
- `confirmDelete(roll)`: Prompt before delete.
- `svalidateStudentForm(formId)`: Simple client-side validation for add/edit forms.

### Example
```html
<form id="addForm" onsubmit="return svalidateStudentForm('addForm')">
  <!-- fields -->
</form>
```
