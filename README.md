### Set up

python3 -m venv ./venv_alg
source ./venv_alg/bin/activate
export PYTHONPATH="${PYTHONPATH}:./" - 'Rexecute the next command from your project dir'
pip3 install -r requirements.txt






#### Cracking the coding interview (algorithms solving advices):

1. **listen carefully** - Yes, you do want to listen to the problem and make sure you heard it correctly. You do want to ask questions about anything you're unsure about.

2. **Draw Example:** When you hear a question, get out of your chair, go to the whiteboard, and draw an example. An example can dramatically improve your ability to solve an interview question

3. **Did you understans the task correctly:** Listen carefully to the problem, and be sure that you've mentally recorded any unique information in the problem.

### Draw example:

1. **Generalize your example:** Be careful. It's very easy to inadvertently draw a special case. Try to make the best example you can. If it later turns out your example isn't quite right, you can and should fix it.

2. **State a Brute Force:** -  It's okay and expected that your initial algorithm won't be very optimal. (You don't want your inter­ viewer to think that you're struggling to see even the easy solution.) It's okay that this initial solution is terrible. Explain what the space and time complexity is, and then dive into improvements.

3. **Recognize algorithms and patterns:** Recognize algorithms and patterns which can be used for the problem solving

4. **Save space on the board:** Implement Start coding in the far top left corner of the whiteboard (you'll need the space). Remember that you only have a short amount of code

5. **One more time** - If you don't understand exactly what you're about to write, you'll struggle to code it!

### 0ptimize your solution

1. **Walk Through the code:** Be sure you have clear vision of the implementation - after you've nailed down an optimal algorithm, don't just dive into coding. Take a moment to solidify your understanding of the algorithm.
Walk through your algorithm and get a feel for the structure of the code. Know what the variables are and when they change.

2. **Precompute information:** Is there a way that you can reorganize the data (sorting, use hashtable, etc.) or compute some values upfront that will help save time in the long run.


3. **Write pseudocode** You can write pseudocode if you'd like. Be careful about what you write, write Basic steps:
- (1) Search array. 
- (2) Find biggest. 
- (3) Insert in heap:

Or brief logic:
("if p < q, move p. else move q") can be valuable. 

But when your pseudocode starts having for loops that are written in plain English, then you're essentially just writing sloppy code. It'd probably be faster to just write the code.




### Optimize&SolveTechnique#1:LookforBUD 

1. **Bottlenecks:** A bottleneck is a part of your algorithm that slows down the overall runtime. 
For example, suppose you have a two-step algorithm:
- The first step isO(N log N) 
- The second step is O(N). 

The first step O(N log N) is the bottleneck despite you improve your second step O(n) to O(1)

2. **Unnecessary work**

<img src="./img/cracking_coding/1_unnec_work.png" alt="Getting started" />

<img src="./img/cracking_coding/2_unnec_work.png" alt="Getting started" />