# Parsons Practice

## Parsons 1
Re-arrange the blocks below so they print out "Hello World!"

<div id="one-sortableTrash" class="sortable-code"></div> 
<div id="one-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="one-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="one-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "int decCount = 0;\n" +
    "for (int row = 0; row &lt; grid.length; row++) {\n" +
    "   boolean isDecreasing = true;\n" +
    "   for (int col = 1; col &lt; grid[0].length; col++) {\n" +
    "      if (grid[row][col] &gt; grid[row][col - 1]) {\n" +
    "         isDecreasing = false;\n" +
    "      }\n" +
    "   }\n" +
    "   if (isDecreasing) {\n" +
    "      decCount++;\n" +
    "   }\n" +
    "}\n" +
    "return decCount;\n" +
    "return isDecreasing; #distractor\n" +
    "if (!isDecreasing) { #distractor\n" +
    "int col = 0; col &lt; grid[0].length; col++ #distractor\n" +
    "int col = 1; col &lt; grid.length; col++ #distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "one-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "trashId": "one-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#one-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#one-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>
</script>

### Implementation Notes

When you host multiple Parson's problems on a single markdown page, you need to add a unique prefix. You can easily do this in the Codio generator by typing a unique prefix into the "Prefix" textbox and pressing Enter/Return. Then you can simply copy-paste like normal.

If want each problem to be it's own page, you can use relative path links at the bottom of each of your markdown pages as seen below. If you want students to be able to return to previous problems in this format, consider adding previous links or link to a table of contents like page.

### Example Next Link
[Next](./parsons/example1.html)
