<h1>2D Array & ArrayList Problems</h1>

<p>Some or all of the below problems will involve distractor blocks, meaning there are some blocks that will not be used. Press the <em>Get Feedback</em> button below the blocks to check if your answer is correct, or use <em>Reset Problem</em> to delete your work. Please drag so that standard indentation is followed. <br><br>

<em>If you want more practice, please go to CSAwesome sections 8.4, 8.5 & 8.6 for 2D arrays; sections 7.10, 7.11 & 7.12 for ArrayList. </em></p>

<h2> 1. Count Decreasing Rows</h2>
<p>A row is in decreasing order if each value is less than or equal to its predecessor. For example, the rows <code>[7, 6, 6, 2]</code> and <code>[4, 3, 2, 1]</code> are in decreasing order, but <code>[5, 8, 9, 0]</code> is not. Re-arrange the blocks to create a method that counts and returns the number of decreasing rows in a 2D array <code>grid</code>. </p>

<div id="2dArr-countDecreasing-sortableTrash" class="sortable-code"></div> 
<div id="2dArr-countDecreasing-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="2dArr-countDecreasing-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="2dArr-countDecreasing-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "public int countDecreasing(int[][] grid) {\n" +
    "  int decCount = 0;\n" +
    "  for (int row = 0; row &lt; grid.length; row++) {\n" +
    "     boolean isDecreasing = true;\n" +
    "     for (int col = 1; col &lt; grid[0].length; col++) {\n" +
    "        if (grid[row][col] &gt; grid[row][col - 1]) {\n" +
    "           isDecreasing = false;\n" +
    "        }\n" +
    "     }\n" +
    "     if (isDecreasing) {\n" +
    "        decCount++;\n" +
    "     }\n" +
    "  }\n" +
    "  return decCount;\n" +
    "}\n" +
    "return isDecreasing; #distractor\n" +
    "if (!isDecreasing) { #distractor\n" +
    "for (int col = 0; col &lt; grid[0].length; col++) {} #distractor\n" +
    "for (int col = 1; col &lt; grid.length; col++) {} #distractor\n" +
    "return false; #distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "2dArr-countDecreasing-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "trashId": "2dArr-countDecreasing-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#2dArr-countDecreasing-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#2dArr-countDecreasing-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>

Bonus: write a method by yourself that counts the number of increasing columns. 

<p hidden>public int countDecreasing(int[][] grid) {
  int decCount = 0;
  for (int row = 0; row < grid.length; row++) {
     boolean isDecreasing = true;
     for (int col = 1; col < grid[0].length; col++) {
        if (grid[row][col] > grid[row][col - 1]) {
           isDecreasing = false;
        }
     }
     if (isDecreasing) {
        decCount++;
     }
  }
  return decCount;
}
</p>

<h2>2. Exam Attendance</h2>

The Student class is defined as follows:

```
class Student {
  private String fullName;
  private String examRegCode;

  /* constructor not shown */

  public String getFullName() { return fullName; }
  public String getExamRegCode() { return examRegCode; }
}
```

A 2D array that simulates desks in an exam hall is defined as `desks` of type `Student[][]`. A 1D array of exam registration codes defined as `codes` represents the expected attendance list. A method is required to search `desks` for each of the students whose exam registration codes are contained in `codes`, and return an `ArrayList<String>` containing the codes of students who are expected to be present but are not in the examination hall. Note that not all desks are occupied, and this is represented by a `null` value. Re-arrange the blocks to define this method. 

<em>Hint: </em> loop through the codes on the outermost loop. 

<div id="2dArr-absentStudents-sortableTrash" class="sortable-code"></div> 
<div id="2dArr-absentStudents-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="2dArr-absentStudents-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="2dArr-absentStudents-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "public ArrayList&lt;String&gt; findAbsentees(Student[][] desks, String[] codes) {\n" +
    "   ArrayList&lt;String&gt; missing = new ArrayList&lt;&gt;();\n" +
    "   for (String code : codes) {\n" +
    "      boolean found = false;\n" +
    "      for (Student[] row : desks) {\n" +
    "         for (Student student : row) {\n" +
    "            if (student != null &amp;&amp; student.getExamRegCode().equals(code)) {\n" +
    "               found = true;\n" +
    "            }\n" +
    "         }\n" +
    "      }\n" +
    "      if (!found) {\n" +
    "         missing.add(code);\n" +
    "      }\n" +
    "   }\n" +
    "   return missing;\n" +
    "}\n" +
    "for (Student row : desks) { #distractor\n" +
    "if (student.getExamRegCode().equals(code)) { #distractor\n" +
    "if (student.getExamRegCode().equals(code) &amp;&amp; student != null) { #distractor\n" +
    "return code; #distractor\n" +
    "if (found) { #distractor\n" +
    "missing.set(code); #distractor\n" +
    "public void findAbsentees(Student[][] desks, String[] codes) { #distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "2dArr-absentStudents-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "trashId": "2dArr-absentStudents-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#2dArr-absentStudents-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#2dArr-absentStudents-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>

<p>Bonus: write a more efficient version by yourself which stops looping once a student code has been found. </p>

<p hidden>

</p>

<h2>3. Remove finished Books from list</h2>

The `Book` class is defined as:

```
class Book {
  private String title;
  private boolean finished;

  /* constructor not shown */
  public String getTitle() { return title; }
  public boolean isFinished() { return finished; }
  public void setFinished(boolean finished) { this.finished = finished; }
}
```

An array of type `String[]` defined as `completed` provides several book titles that have been finished. The `books` list is an `ArrayList<Book>` object that stores several book objects. The task is to define a method that will iterate through `books` and do the following:

* set `finished` to `true` for all books that are found in `completed`.
* remove all books that are finished, including both those which were just updated due to the previous requirement, and which were already marked as finished.
* return an `ArrayList<Book>` that contains references to all books which were removed. 

Rearrange the blocks to complete the method. *Hint: loop through the book titles on the outermost loop*

<div id="arrayList-finishedBooks-sortableTrash" class="sortable-code"></div> 
<div id="arrayList-finishedBooks-sortable" class="sortable-code"></div> 
<div style="clear:both;"></div> 
<p> 
    <input id="arrayList-finishedBooks-feedbackLink" value="Get Feedback" type="button" /> 
    <input id="arrayList-finishedBooks-newInstanceLink" value="Reset Problem" type="button" /> 
</p> 
<script type="text/javascript"> 
(function(){
  var initial = "public ArrayList&lt;Book&gt; removeFinished(String[] finished, ArrayList&lt;Book&gt; books) {\n" +
    "   ArrayList&lt;Book&gt; removed = new ArrayList&lt;&gt;();\n" +
    "   for (String bookTitle : finished) {\n" +
    "      for (int i = 0; i &lt; books.size(); i++) {\n" +
    "         if (bookTitle.equals(books.get(i).getTitle())) {\n" +
    "            books.get(i).setFinished(true);\n" +
    "         }\n" +
    "         if (books.get(i).isFinished()) {\n" +
    "            removed.add(books.remove(i));\n" +
    "            i--;\n" +
    "         }\n" +
    "      }\n" +
    "   }\n" +
    "   return removed;\n" +
    "}\n" +
    "for (int i = 0; i &lt; books.length; i++) { #distractor\n" +
    "if (bookTitle == books.get(i).getTitle())) { #distractor\n" +
    "if (bookTitle == books.get(i)) { #distractor\n" +
    "i++; #distractor\n" +
    "removed.add(books.get(i)); #distractor\n" +
    "return books.get(i); #distractor";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "arrayList-finishedBooks-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "trashId": "arrayList-finishedBooks-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#arrayList-finishedBooks-newInstanceLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.shuffleLines(); 
  }); 
  $("#arrayList-finishedBooks-feedbackLink").click(function(event){ 
      event.preventDefault(); 
      parsonsPuzzle.getFeedback(); 
  }); 
})(); 
</script>

