# 2D Array Problems

Some or all of the below problems will involve distractor blocks, meaning there are some blocks that will not be used. Press the **Get Feedback** button below the blocks to check if your answer is correct, or use **Reset Problem** to delete your work. Please drag so that standard indentation is followed. 

## 1. Count Descending Rows
A row is in descending order if each value is less than or equal to its predecessor. For example, the rows `[7, 6, 6, 2]` and `[4, 3, 2, 1]` are in decreasing order, but `[5, 8, 9, 0]` is not. Re-arrange the blocks to create a method that counts and returns the number of decreasing rows in a 2D array `grid`. 

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


