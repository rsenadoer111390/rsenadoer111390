<html>
<head>
    <title>Branch Search</title>
    <style>
        /* Define the background image */
        body {
            background-image: url('your-background-image.jpg'); /* Replace 'your-background-image.jpg' with the path to your image */
            background-size: cover;
            background-position: center;
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        /* Style the search bar and button */
        h1 {
            color: blue; /* Change text color to blue */
            font-size: 36px;
        }

        #searchInput {
            padding: 10px;
            width: 300px;
            border: none;
            border-radius: 24px;
            font-size: 18px;
            margin: 10px;
        }

        #searchButton {
            padding: 12px 24px;
            background-color: #4285f4;
            color: white;
            border: none;
            border-radius: 24px;
            cursor: pointer;
            font-size: 18px;
        }

        #searchResults {
            margin-top: 20px;
            text-align: center;
            color: blue; /* Change text color to blue */
        }
    </style>
</head>
<body>
    <h1>Branch Search</h1>
    <input type="text" id="searchInput" placeholder="Enter branch name">
    <button id="searchButton">Search</button>
    <div id="searchResults"></div>
</body>

<script>
    // Define an array of branch names and their corresponding branch codes
    const branches = [
        { name: "Dumaguete 1", code: "147" },
        { name: "Dumaguete 2", code: "149" },
        { name: "Dumaguete 3", code: "151" },
        { name: "Dumaguete 4", code: "152" },
        { name: "Dumaguete 5", code: "853" },
        { name: "Dumaguete 6", code: "806" },
        { name: "Dumaguete 7", code: "972" },
        { name: "Foundation", code: "631" },
        { name: "Poblacion 8", code: "756" },
        { name: "Real", code: "330" },
        { name: "Market Place", code: "447" },
        { name: "Taclobo", code: "541" },
        { name: "Amlan", code: "758" },
        { name: "Bais 1", code: "144" },
        { name: "Bais 2", code: "584" },
        { name: "Bais 3", code: "418" },
        { name: "Lindbergh", code: "740" },
        { name: "Lumbangan", code: "798" },
        { name: "Mabinay", code: "529" },
        { name: "Pamplona", code: "716" },
        { name: "San Jose", code: "899" },
        { name: "Tanjay 1", code: "160" },
        { name: "Tanjay 2", code: "161" },
        { name: "Capitol", code: "015" },
        { name: "Dumaguete 8", code: "974" },
        { name: "Larena", code: "155" },
        { name: "Lazi", code: "156" },
        { name: "Looc", code: "329" },
        { name: "Maria", code: "315" },
        { name: "Saint Paul", code: "975" },
        { name: "San Juan", code: "813" },
        { name: "Sibulan", code: "305" },
        { name: "Siquijor", code: "158" },
        { name: "Robinson's", code: "653" },
        { name: "Bagacay", code: "148" },
        { name: "Banilad", code: "689" },
        { name: "Basay", code: "678" },
        { name: "Bayawan 1", code: "145" },
        { name: "Bayawan 2", code: "595" },
        { name: "Magsaysay", code: "620" },
        { name: "Bonawon", code: "324" },
        { name: "Dauin", code: "576" },
        { name: "Siaton", code: "157" },
        { name: "Sta. Catalina", code: "159" },
        { name: "Valencia", code: "764" },
        { name: "Zamboanguita", code: "539" },
        { name: "Ayungon", code: "808" },
        { name: "Bindoy", code: "016" },
        { name: "Canlaon 1", code: "146" },
        { name: "Canlaon 2", code: "588" },
        { name: "Guihulngan", code: "153" },
        { name: "Jimalalud", code: "154" },
        { name: "Hilaitan", code: "456" },
        { name: "La Libertad", code: "744" },
        { name: "Manjuyod", code: "530" },
        { name: "Tayasan", code: "657" },
        { name: "Zulueta", code: "820" },
        { name: "Vallehermoso", code: "035" }
        // Add more branches here...
    ];

    // Get references to the input, button, and results div
    const searchInput = document.getElementById('searchInput');
    const searchButton = document.getElementById('searchButton');
    const searchResults = document.getElementById('searchResults');

    // Function to perform the search
    function performSearch() {
        // Get the search query from the input field
        const query = searchInput.value.toLowerCase();

        // Filter the branches array based on the search query
        const matchingBranches = branches.filter(branch => branch.name.toLowerCase().includes(query));

        // Display the matching branches in the results div
        if (matchingBranches.length > 0) {
            const resultsHTML = matchingBranches.map(branch => `<p>${branch.name} - Branch Code: ${branch.code}</p>`).join('');
            searchResults.innerHTML = resultsHTML;
        } else {
            searchResults.innerHTML = "<p>No matching branches found.</p>";
        }
    }

    // Event listener for the Enter key press in the search input
    searchInput.addEventListener('keyup', function(event) {
        if (event.key === 'Enter') {
            performSearch();
        }
    });

    // Event listener for the search button click
    searchButton.addEventListener('click', performSearch);
</script>
</html>
