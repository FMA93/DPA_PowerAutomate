# Hex Breaker Tech - Episode 4: Excluding Weekends in Project Planning Using Power Automate

Welcome back to Hex Breaker Tech, where we unravel complex automation spells and hexes with ease! In this episode, we’re diving into the world of project planning. We'll guide you through setting up a Power Automate flow that plans projects over a set number of days while skillfully skipping those pesky weekends. Let's break this hex and bring your projects into perfect alignment!

## Flow Breakdown

### Step 1: Manual Trigger
This flow starts with a manual trigger, giving you the control to initiate the process whenever needed.

### Step 2: Initialize Variables
- Start Date String Variable: Set this to the project start date in ISO 8601 format. This is your project’s starting point in time.
- Integer Variable i: Initialize this with a value of 1. It will serve as our loop counter.
- Project Days Integer Variable: Define the number of project days. For this example, we use 21.

### Step 3: Loop - Do Until Variable `i` > `Project Days`
This loop is where the magic happens, iterating through each project day until the total number of project days is reached.

#### 3.1: Compose Weekend Check
We ensure that weekends are excluded by using this formula:

```plaintext
addDays(variables('ProjectStart'), if(equals(dayOfWeek(variables('ProjectStart')), 6), 2, if(equals(dayOfWeek(variables('ProjectStart')), 7), 1, 0)))
```

This formula adds days to the start date, skipping weekends if the start date lands on a Saturday or Sunday.

#### 3.2: Compose Day Name
Next, we determine the day name for each planned project day using:

```plaintext
formatDateTime(outputs('Compose_Weekend_Check'), 'dddd')
```

This converts the date into a readable day name, like "Monday" or "Friday".

#### 3.3: Add a Row into an Excel Table
We then log the planned project day into an Excel table with the following columns:

- Project Date: 
    ```plaintext
    concat('''',formatDateTime(outputs('Compose_Weekend_Check'), 'dd-MM-yyyy'))
    ```
- Project Day: This uses the output from the "Compose Day Name" step.

#### 3.4: Compose Next Day
Calculate the next project day using:

```plaintext
addDays(outputs('Compose_Weekend_Check'), 1)
```

This ensures our flow moves to the following day.

#### 3.5: Update Project Start Date Variable
The start date variable is updated with the output from the "Compose Next Day" step, setting the stage for the next loop iteration.

#### 3.6: Increment i Variable by 1
Finally, we increment the loop counter variable `i` by 1 to continue the loop until all project days are planned.

### Final Result
This loop continues until all project days are accounted for, with weekends skipped and the details recorded in your Excel table. And just like that, you’ve got a fully planned project that deftly avoids weekends!

## Conclusion
In this episode of Hex Breaker Tech, you’ve learned how to plan a project over several days while skipping weekends using Power Automate. Whether you’re a novice or a seasoned pro, this flow will keep your projects on track and on time. Stay tuned for more automation sorcery from Hex Breaker Tech!
```
