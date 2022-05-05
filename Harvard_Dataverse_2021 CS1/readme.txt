This dataset includes keystrokes and other data from a CS1 (CS 1400) course at
Utah State University taught in Fall 2021. Files include:

* keystrokes.csv - Keystrokes in mostly compliant ProgSnap2 format. See
  https://cssplice.github.io/progsnap2/ProgSnap2-v8-18Dec2020.pdf.
  Differences in columns from ProgSnap2 are:
  ** SourceLocation - One-dimensional index of the linearized program. The
     standard requires a line and column. We use a single index for efficiency
     purposes. For space purposes it is not prefixed by "text:" as given in the
     standard.
  ** Code state is not maintained, so CodeStateID is always nan.
  ** ClientTimestamp - see note on timestamps at the end of this file.

* runs.csv - Record of execution runs. This file is very big because it
  includes all output from every run, so if a student had an infinite loop
  there are many lines in the CSV. To filter these out, filter out rows with
  'o' in the Action column.

* students.csv - Grades, ACT score, GPA, and major for each student.

* due.csv - Due dates for the assignments.

* Assignment Descriptions - Descriptions for each of the assignments.

All timestamps in keystrokes.csv and runs.csv are from Java's
System.CurrentTimeMillis(), which gives Unix Epoch time in UTC. due.csv has
MDT/MST, UTC, and ms since the Unix epoch versions of the due dates.
