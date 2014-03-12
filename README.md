Margin Viewer for Annotator
==================
##Margin viewer Annotator Plugin

view_annotator.js is a plugin for Annotator to view the current annotations in a panel in the right side.


##Installation

To use the tool you need to install the [Annotator plugin](https://github.com/okfn/annotator/) to annotate text. 


```html
    <script src="../lib/jquery-1.9.1.js"></script>
    <script src="../lib/annotator-full.1.2.9/annotator-full.min.js"></script>
    <!-- Locale for language -->
    <script src="../lib/jquery-i18n-master/jquery.i18n.min.js"></script>
    <!-- For show the annotation creation date -->
    <script src="../lib/jquery.dateFormat.js"></script>
    <!-- File with the translations -->
    <script src="../locale/en/annotator.js"></script>
    <!-- annotator -->
    <link rel="stylesheet" href="../lib/annotator-full.1.2.9/annotator.min.css">
    <link rel="stylesheet" href="../src/css/style.css">
    <!-- anotator plug in -->
    <script src="../src/view_annotator.js"></script>
    <script>
      jQuery(function ($) {
          $.i18n.load(i18n_dict);
         // Customise the default plugin options with the third argument.
          var annotator = $('body').annotator().annotator().data('annotator');
          var propietary = 'demoUser';
          annotator.addPlugin('Permissions', {
                        user: propietary,
                        permissions: {
                            'read': [propietary],
                            'update': [propietary],
                            'delete': [propietary],
                            'admin': [propietary]
                        },
                        showViewPermissionsCheckbox: true,
                        showEditPermissionsCheckbox: false
            });
            // Calling annotator viewer plug in -->
            $('body').annotator().annotator('addPlugin', 'visorAnotacions');});
  </script>
```
##Development
Each annotation in the right panel needs a unique Id, annotator when use a back end assigns a Unique Id to each annotation, this will be correct Id to assign to each annotation in the view panel, but in this implementation, with no store plug in, we generate the unique Id with a function.

##Demo
Demo in demo/anotacions.html
