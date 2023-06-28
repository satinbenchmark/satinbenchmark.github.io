---
layout: default
title: SATIN Public Leaderboard
---

# SATIN Leaderboard

<section>
    <p>Welcome to the SATIN Project Public Leaderboard! Here, you can view the latest rankings of models and their performance on the SATIN benchmark.</p>
</section>

<div id="leaderboard"></div>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/PapaParse/5.3.0/papaparse.min.js"></script>

<script>
// URL of the Google Sheet published as CSV
var url = 'https://docs.google.com/spreadsheets/d/e/2PACX-1vSyuLKK-omWVj5NqzFBjxPW_qZpB9AuGs6iJhf7lqBm2VHHdvAdHNdf6V_13cdqehMq1O9Eiw2mT-JQ/pub?gid=617390435&single=true&output=csv';

$.get(url, function(data) {
    // Parse the CSV data
    var csvData = Papa.parse(data).data;

    // Find the index of the 'SATIN' column
    var satinIndex = csvData[0].findIndex(header => header === 'SATIN');
    if (satinIndex === -1) {
        console.error("No 'SATIN' column found!");
        return;
    }

    // Sort the data by the SATIN column
    csvData.sort(function(a, b) {
        return b[satinIndex] - a[satinIndex];
    });

    // Remove the first column from each row
    for (var i = 0; i < csvData.length; i++) {
        csvData[i].splice(0, 1);  // remove the first element from each row
    }


    // Add a placeholder for ranking to each row (excluding the header row)
    for (var i = 1; i < csvData.length; i++) {
        csvData[i].unshift(null);
    }

    // Extract the data (excluding the header), sort it, and then reassign it to csvData
    csvData = [csvData[0]].concat(csvData.slice(1).sort((a, b) => b[satinIndex] - a[satinIndex]));

    // Assign rankings, taking into account equal scores
    var rank = 1;  // start ranking at 1
    var rankCount = 1;  // initialize count of rows ranked
    csvData[1][0] = rank;  // assign first rank

    for (var i = 2; i < csvData.length; i++) {
        rankCount++;  // increment count of rows ranked
        if (csvData[i][satinIndex] !== csvData[i-1][satinIndex]) {
            // if scores are not equal, update the rank to the current row count
            rank = rankCount;
        }
        // assign current rank
        csvData[i][0] = rank;
    }



    csvData[0].unshift('Rank')


    // Create a table and add it to the #leaderboard div
    var table = $('<table></table>');

    // Add the custom headers
    var headerRow1 = $('<tr></tr>');
    var header0 = $('<th></th>').text('Submission').attr('colspan', 2).css('text-align', 'center').css('font-weight', 'bold');
    var header1 = $('<th></th>').text('Model').attr('colspan', 3).css('text-align', 'center').css('font-weight', 'bold');
    var header2 = $('<th></th>').text('0-Shot Classification Accuracy').attr('colspan', 7).css('text-align', 'center').css('font-weight', 'bold');
    var header3 = $('<th></th>').text('URL').attr('colspan', 1).css('text-align', 'center').css('font-weight', 'bold');
    headerRow1.append(header0, header1, header2, header3);
    table.append(headerRow1);



    // Add the rest of the rows
        for (var i = 0; i < csvData.length; i++) {
            // Skip the row if the first column is '#N/A'
            if (csvData[i][1] === '#N/A') {
                continue;
            }
            var row = $('<tr></tr>');
            for (var j = 0; j < csvData[i].length; j++) {
                var cell = $('<td></td>');

                // If this is the URL column (e.g., column 13), create a hyperlink
                if (i>=1 && j === satinIndex+1) {
                    var link = $('<a></a>').attr('href', csvData[i][j]).text('🔗');
                    cell.append(link);
                } else {
                    cell.text(csvData[i][j]);

                    // If this is the first row of data, make the text italic
                    if (i === 0) {
                        cell.css('font-style', 'italic');
                    }
                }

                row.append(cell);
            }
            table.append(row);
    }
    $('#leaderboard').append(table);
});
</script>

<p>We encourage you to submit your own model's results to be featured on the SATIN Public Leaderboard! By sharing your work, you contribute to the growth and advancement of the remote sensing and machine learning community.</p>
<p>To submit your results, please follow the guidelines outlined in our submission instructions using the button below.</p>

<a href="https://forms.gle/5vHfryQT5se1Dg4e6" class="button">Submit</a>
