# Add and Remove Buttons
Javascript (and necessary HTML attributes) for enabling add and remove buttons for form input fields or sections.

## Usage
The script uses a few HTML attributes to connect every button with the element it is cloning and it's corresponding add/delete button.  This allows one general function to be called and using the clicked button's attributes we can get all the information we need.  All you have to do is ensure your HTML elements contain the appropriate attributes as detailed below, link to the script, and you will have fully functioning add and remove buttons.

Here is a sample HTML setup we'll use to walk through the attributes the script requires (you can check out the basic demo [here](http://codepen.io/anon/pen/KaPmBb/))

```html
<!-- Section being added/removed -->
<div style="display: none" id="section0" data-clone="section">

  <!-- Field being added/removed within larger section -->
  <div style="display: none" id="section0input0" data-clone="section0input" data-field="input">
    <input type="text" placeholder="Fill me in!" />
  </div>
  
  <!--  Add button for field  -->
  <input type="button" id="section0btnAdd0" for="section0input0" data-btn-del="section0btnDel0"
  class="btnAdd" data-text="Add Field" value="Add Field" />
  
  <!--  Remove button for field   -->
  <input type="button" id="section0btnDel0" for="section0input0" data-btn-add="section0btnAdd0"
  class="btnDel" value="Remove Button" disabled="" />           
</div>

<!-- Add button for section -->
<input type="button" id="btnAdd0" for="section0" data-btn-del="btnDel0"
class="btnAdd" data-text="Add Section" value="Add Section" />

<!-- Remove button for section -->
<input type="button" id="btnDel0" for="section0" data-btn-add="btnAdd0"
class="btnDel" value="Remove Button" disabled="" /> 
```

```data-clone``` attribute allows us to count the number of cloned fields that exist (the ```id``` of each new field being the                  value of ```data-clone``` + the number of cloned fields that exists.

```data-field``` attribute is for nested cloned fields, used to appropriate alter the ```id``` attribute of inner elements.

```btnAdd``` class is used to bind the javascript function to add buttons, as well as count the amount of add buttons (and                  therefore remove buttons and fields) within the larger cloned section.

```btnDel``` class is used to bind the javascript function to remove buttons, as well as count the amount of add buttons (and              therefore remove buttons and fields) within the larger cloned section.

```for``` attribute is the ```id``` of the field the button adds or removes.

```data-btn-del``` attribute is the ```id``` of the corresponding remove button.

```data-btn-add``` attribute is the ```id``` of the corresponding add button

```data-text``` attribute is used to change the text of the add button back to it's original value after it the text is change                 when the limit of cloned fields is reached.

