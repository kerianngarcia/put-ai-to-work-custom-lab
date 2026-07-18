# NASK Tool 2: Lookup Assignment Groups


Following the previous steps to add another script tool, this time name it \*\*assignmentgroup\*\*:

      ```javascript
      (function runScript(context) {
      var groups = [];
      // Resolve the sys\_id of the 'itil' group type (avoid hardcoding)
      var itilTypeSysId = '';
      var typeGR = new GlideRecord('sys\_user\_group\_type');
      typeGR.addQuery('name', 'itil');
      typeGR.setLimit(1);
      typeGR.query();
      if (typeGR.next()) {
      itilTypeSysId = typeGR.getUniqueValue();
      }
      // Query: active=true AND (type IS EMPTY OR type CONTAINS itil)
      var gr = new GlideRecord('sys\_user\_group');
      gr.addActiveQuery();
      var qc = gr.addNullQuery('type');
      if (itilTypeSysId) {
      qc.addOrCondition('type', 'CONTAINS', itilTypeSysId);
      }
      gr.query();
      while (gr.next()) {
      groups.push({
      sys\_id: gr.getUniqueValue(),
      name: gr.getValue('name') || '',
      description: gr.getValue('description') || ''
      });
      }
      return JSON.stringify(groups);
      })(context);
      ```

Configuration should now look like this:


![](../../.gitbook/assets/section-8/S8.1-8.png)

Again, no other configuration is needed select continue until you have added the tool. Your flow should look similar to the image below. The exact order does not matter as both scripts will execute prior to the prompt.


![](../../.gitbook/assets/section-8/S8.1-9.png)

To control, check back with your prompt, the \{{inputs\}} should be blue indicating that they are matched with the tools you have added.


![](../../.gitbook/assets/section-8/S8.1-10.png)
