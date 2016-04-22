# One-to-Many Match to Sample Task for Three Three-Member Classes (MTS - OtM 3x3)

## License
Copyright (c) Ian Hussey 2016 (ian.hussey@ugent.be)

Distributed under the MIT license.

## Version
0.7 (19/4/2016)

Written in PsychoPy 1.82.01

*NB This implimention is still in development and has not been used in a study yet.* 

## Task structure
Trains three three-member classes: A1-B1-C1, A2-B2-C2, and A3-B3-C3 via one-to-many match to sample training; then assesses for emergent B-C (equivalence) relations.

- Training block contains 18 trials contain each contain a fully counterbalanced set of A1, A2 and A3 sample stimuli with the required target stimulus counterbalanced across all three stimuli locations. The location of the incorrect comparison stimuli is randomised for each trial.
- If the training crition of X number of correct trials within a block is met, participants proceed to the testing block. Default is 16 (out of 18: 89%).
- Otherwise, participants repeat the training block. This is done a max number of times set by max_training.
- Testing block contains 9 C-B (i.e. equivalence) trials. Symmetry relations could be added simply by modiying the task structure file.
-  If the testing crition of x number of correct trials within a block is met, the task ends with a "passed" message. Default is 8 (out of 9: 89%).
- Otherwise, participants repeat both the training and testing blocks. Participants must again meet the training criterion to move on to the testing blocks. This is done a max number of times set by max_training_and_testing.
- By setting the training crition to 0 you can alter the structure of the task to that participants recieve loops of training and testing rather than requiring them to meet a training accuracy crition before being exposed to the testing blocks.  

## Notes
- The last row of a participant's .csv data file specifies whether they passed or failed the task under the "passed_training" column.
- For demonstration and testing purposes the task present the stimuli as "A1", "C2" etc. To use word stimuli simply alter the stimuli.xlsx file (or replace it with the "stimuli ALT - ARBITRARY.xlsx" file which contains nonsense words.
- All instructions, stimuli and several task parameters are set via the "stimuli, instructions and parameters.xlsx" file.
- Full unicode support: one could use chinese characters etc as word stimuli, or tranlsate the task in to other languages simply by modifying the stimuli file. 
- No support for image stimuli at present, but this would be trivial to add. For example, change TextComponents for ImageComponents and put image1.jpg etc in the stimulus file. All counterbalancing, block structure, etc is taken care of elsewhere.
- Press return to end the task at the end of task screen.

## Known issues
None.

## To do
- R script for data processing needs updating
- Reasonable default parameters must be chosen, e.g., with reference to a specific previous experiment.

## Changelog
### 0.7
Many changes. 
- Intigrated training and testing into one task. 
- All strings in stimuli file, as well as several task parameters.
- Several training and testing methods available based on the pairs of mastery criteria, block length multipliers, and max reps variables.

### 0.6
Moved loop.finished code to a new postblock routine so that the full block is completed. 

### 0.5
1. Extra variables saved to .csv files: pass/fail training, exemplars used on each trial, current N-in-a-row.
2. Full screen.
3. Saves log file.

### 0.4
1. Code solution to randomised location of incorrect target stimuli. block_layout file reorganised to refer to required, incorrect1 and incorrect2 stimuli and specify required response. Based on required response, the contents of this location is filled with the required answer. The contents of the other two targets are then shuffle-pop()'d. Block length is therefore more flexible now. 
2. N-in-a-row mastery criterion now in excel file.

### 0.3
Now has proper counterbalancing of location of incorrect taret stimuli, but this is done via full permutations in the stimulus file. If you want a block length smaller than 36 trials then a coder solution would be needed.

### 0.2
Seperate files for block structure and exemplars, plus code to populate the sample and target stimuli boxes on a trial by trial basis.

### 0.1
Stimuli pulled from single file however, therefore this file conflates block structure with stimulus exemplars.