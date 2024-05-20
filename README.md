# Welcome to Bug Wrangler Ranch

This first self-assessment is for you to hone several Core Skills that you need as a software developer.

Taking your time now to be thorough, reflective, patient and curious will give you the foundation to be successful throughout the rest of this course and your career.

If you rush this, or think of it as a test to be "passed", then you will already be on the wrong path.

> 🧨 Make sure you answer the vocabulary and understanding questions at the end of this document before notifying your coaches that you are done with the project

## Description

Slim Jenkins offers a vacation package for people who have always wanted to join a cattle driving team across the American Midwest.

He calls it the **Kansas Slim's Cattle Adventure**.

People join a team of experienced drovers who will train them in the basics of herding cattle and driving them across hundreds of miles to their destination at Old Red's Ranch.

Unfortunately, someone gained access to the code that produces an outline of the adventure to the paying customers, so Slim has hired you to examine and fix the code.

## Learning Objectives

Here are your learning objectives for this self-assessment.

1. Able to use the debugger to step through existing code to discover root causes of bugs.
2. Drawing a sequence diagram for a project.
   > Use the [sequencediagram.org](https://sequencediagram.org/) site to generate your sequence diagram. Make sure you save your work as you go.
3. Demonstrate learning efficiency by researching concepts you haven't seen before using your peers, mentors, and the World Wide Web as resources.
4. Awareness of when you need help, and then seeking it out.

## Starter Code

Slim Jenkins has the existing code on Github, so you need to download it from there. Actually, developers call this process _cloning a repository_.

In your terminal, to go your workspace directory.

```sh
cd ~/workspace
```

Then clone the repository to your machine with the following command.

```sh
git clone https://github.com/Nashville-Software-School-Assessments/bug-wrangler-ranch.git
```

This will create a new sub-directory called `bug-wrangler-ranch`. Use the `cd` command to navigate into that directory and open it in VS Code.

```sh
cd bug-wrangler-ranch
code .
```

Open the `main.js` and create your `launch.json` so that you can debug the code starting with `main.js`. Then run the program and start the investigation.

## Example Output

If you are able to fix all of the bugs, you will output similar to what is below.

```sh
************************************************
**  K A N S A S   S L I M ' S   C A T T L E   **
************************************************

\|/         (__)
     '------(oo)
       ||   (__)               \|/
       ||w--||     \|/
   \|/
            \|/                     (__)
                             '------(oo)
                               ||   (__)
                               ||w--||     \|/

You will be accompanying 5 drovers as they drive 50 cattle to Old Red's Ranch for grazing

The herd is made of up the following types of cattle:
Ankole-Watusi,Brown Swiss,Brown Swiss,American Angus,Brown Swiss,
Ankina,American Angus,Ankina,Brown Swiss,Ankole-Watusi,Brown Swiss,
Brown Swiss,American Angus,Ankina,Ankole-Watusi,Brown Swiss,Brown Swiss,
Ankina,Brown Swiss,Ankina,Ankole-Watusi,Brown Swiss,Brown Swiss,
Ankole-Watusi,American Angus,Brown Swiss,American Angus,Ankole-Watusi,
Ankole-Watusi,American Angus,Ankina,Ankina,Ankina,Ankole-Watusi,
American Angus,Brown Swiss,American Angus,Brown Swiss,American Angus,
American Angus,Ankina,Brown Swiss,American Angus,Ankina,Brown Swiss,
American Angus,Ankole-Watusi,Ankina,American Angus,Brown Swiss

Here is the team of drovers you will be joining
        * Melvyn Hethron
        * Yancy Gresley
        * Willabella Attarge
        * Ynes Gyenes
        * Farlie Spere


Your journey will take you through the wildness of the American Midwest and across the following terrain
        * forest
        * plain
        * river
        * mountain
```

## Vocabulary and Understanding

> 🧨 Before you click the "Assessment Complete" button on the Learning Platform, add your answers below for each question and make a commit. It is your option to request a face-to-face meeting with a coach for a vocabulary review.

1. In the **main** module, one of the first lines of code is `const drovers = hireDrovers(cattleToDrive)`. Explain what the value of the `drovers` variable is when that line of code runs.
   > The variable `drovers` has a value equivalent to the return value of the `hireDrovers()` function. The function is being passed the argument of `cattleToDrive` which was initialized as "50".  The function then accepts that argument through its parameter `herdSize` and returns a random array of 5 `drovers` thus setting the value of the `drovers` variable in the main module to the array of 5 random objects pulled from the drovers array nested within the database array.
2. At the bottom of the main module, you will see the following code - `for (const drover of drovers)`. Explain what the values of both the `drover` and the `drovers` variables are.
   > The `drovers` variable has the same value here as it does from the previous question.  The variable `drover` is being initialized as the first object in the `drovers` array. As the for...of loop executes, it will iterate through the `drovers` array and change the value of `drover` to the next object in the array. 
3. In the **journey** module, there is a `journeyMaker()` function. In that function, there is a variable named `areas` which will have the value of an object. Use your debugger to show what the value of each key is on that object. Use [Loom](https://www.loom.com) to record your session.
   > (https://www.loom.com/share/49a08ebea21c431f8d30dd47f214fb10?sid=2bfb7fd1-3e1b-48f5-9b05-57226d7dd90f)
4. Also in the **journey** module, there is the following code:
   ```js
   for (let forestNumber = 0; forestNumber < areas.forests; forestNumber++) {
      journey.push("forest")
   }
   ```
   Explain this code with your best vocabulary.
   > This is a for loop within the `journeyMaker()` function.  Within the parenthesis we begin by initializing the variable `forestNumber` and setting its value to 0. Then, separated by a semicolon, we give the loop a condition to check. In this case, we are checking to see if our variable `forestNumber` (currently 0) is less than the value of the key `forests` within the `areas` object. If the condition is true, we then move to the next line and use the 
   '.push()' method on the `journey` array, pushing the string "forest".  Then we head back up to the third part of the for loop and increment the variable `forestNumber` by one.  The whole loop will repeat until the condition between the semicolons equates to false, and we exit the for loop.
5. Explain the value of the `database` variable in the **database** module. Be as comprehensive as possible.
   > The variable `database` is an object with two key-value pairs. The keys are `cattleTypes` and `drovers`.  The key `cattleTypes` has an nested array with 4 more objects each containing 2 key-value pairs, `id` and `breed`.  The key `drovers` has a total of 50 objects each containing 4 properties.
6. In the **drovers** module, there is a `hireDrovers()` function. You will notice the following code on that line - `(herdSize)`. What is that defining, and where does it get its value?
   > `(herdSize)` is the parameter of the function. It gets its value when the function is called and passed an argument. An example of this is on line 6 of the main module. The `hireDrovers()` function is called passing the argument 
   `(cattleToDrive)` which was initialized as 50 on line 5, thus setting the value of the parameter `(herdSize)` to 50.


## Final Step

Now you need to upload your code to Github so a coach can review it and the answers to your vocabulary and understanding questions. Watch the <a href="https://app.screencastify.com/v3/watch/AwPn0FXfji60TxHuUVkU" target="_blank">Sharing assessment repository<a> video for instructions on how to do it.
