---
layout: page
title: My Journey
permalink: /KanhayPage1/
---
The installation of all the tools was fairly easy, once I found the proper documentation. I didnt struggle to install WSL, but I did originally try to install all the needed applications manually through WSL, but later on, I found out that I had to clone a github repository, and then run a script which would download everything that I needed. Overall, after finding the proper documentation, the installation process was fairly easy.


<!-- Title -->
<h2>Tool Check: 1.8 out of 2</h2>

<!-- Help Message -->
<h3>Input scores, press tab to add each new number.</h3>

<!-- Totals -->
<ul>
    <li>Total: <span id="total">0.0</span></li>
    <li>Count: <span id="count">0.0</span></li>
    <li>Average: <span id="average">0.0</span></li>
</ul>

<!-- Table for Scores -->
<table id="scores-table" border="1">
    <thead>
        <tr>
            <th>Assignment</th>
            <th>Score</th>
            <th>Maximum</th>
        </tr>
    </thead>
    <tbody id="scores"></tbody>
</table>

<!-- Clear button -->
<button id="clear-storage">Clear Saved Scores</button>

<script>
// Load scores from localStorage
window.onload = function() {
    if (localStorage.getItem('scoresData')) {
        const scoresData = JSON.parse(localStorage.getItem('scoresData'));
        scoresData.forEach(data => {
            addScoreRow(data.assignment, data.score, data.max);
        });
    } else {
        newInputLine(0);
    }
};

// Executes on input event and calculates totals
function calculator(event) {
    var key = event.key;
    if (key === "Tab" || key === "Enter") {
        event.preventDefault();
        var array = document.getElementsByName('score');
        var total = 0;
        var count = 0;

        for (var i = 0; i < array.length; i++) {
            var value = array[i].value;
            if (parseFloat(value)) {
                total += parseFloat(value);
                count++;
            }
        }

        // Update totals
        document.getElementById('total').innerHTML = total.toFixed(2);
        document.getElementById('count').innerHTML = count;

        if (count > 0) {
            document.getElementById('average').innerHTML = (total / count).toFixed(2);
        } else {
            document.getElementById('average').innerHTML = "0.0";
        }

        if (count === document.getElementsByName('score').length) {
            newInputLine(count);
        }
    }
}

// Adds a new input line in the table
function newInputLine(index) {
    const table = document.getElementById('scores');
    
    const row = table.insertRow(); // Create a new row
    const cell1 = row.insertCell(0);
    const cell2 = row.insertCell(1);
    const cell3 = row.insertCell(2);

    // Label for assignment
    const label = document.createElement('label');
    label.innerHTML = `Assignment ${index + 1}`;
    cell1.appendChild(label);

    // Input for score
    const score = document.createElement('input');
    score.type = 'number';
    score.name = 'score';
    score.style.textAlign = 'right';
    score.style.width = '5em';
    score.onkeydown = calculator;
    cell2.appendChild(score);

    // Max score (static, e.g., 2.0)
    const maxScore = document.createTextNode('2.0');
    cell3.appendChild(maxScore);

    score.focus();
}

// Save score rows in localStorage
function saveScores() {
    const rows = document.querySelectorAll('#scores tr');
    const scoresData = [];
    rows.forEach(row => {
        const assignment = row.cells[0].innerText;
        const score = row.cells[1].querySelector('input').value;
        const max = row.cells[2].innerText;
        scoresData.push({ assignment, score, max });
    });
    localStorage.setItem('scoresData', JSON.stringify(scoresData));
}

// Adds a new row with stored data on page load
function addScoreRow(assignment, score, max) {
    const table = document.getElementById('scores');
    const row = table.insertRow();
    const cell1 = row.insertCell(0);
    const cell2 = row.insertCell(1);
    const cell3 = row.insertCell(2);

    cell1.innerText = assignment;
    const input = document.createElement('input');
    input.type = 'number';
    input.name = 'score';
    input.style.textAlign = 'right';
    input.style.width = '5em';
    input.value = score;
    input.onkeydown = calculator;
    cell2.appendChild(input);
    cell3.innerText = max;
}

// Clear localStorage
document.getElementById('clear-storage').addEventListener('click', () => {
    localStorage.removeItem('scoresData');
    location.reload();
});

// Save scores on window unload
window.onbeforeunload = saveScores;
</script>
