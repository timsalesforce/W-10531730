# Pinned Region scrollIntoView bug
# Repro
- Deploy the metadata here
- Create a new Work Order
- Open the Work Order (notice the pinned header flexipage)
- Scroll down in the related list pane, and create a new Instruction__c object
- Make sure your window height is small, so that the long text fields on the form are off the bottom of the page
- Scroll down so that one of the long text fields is just visible (not the entire field)
- Click in the field

Observe that the page scrolls the main window instead of the form element, causing the element to bleed up into the pinned header
scrollIntoView is used here, and for some reason with Work Order and a custom child object, it behaves this way
It works fine for Account as the parent
