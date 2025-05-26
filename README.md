<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Arunima Bollampally's GitHub Portfolio</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 2em;
            background-color: #f9f9f9;
            color: #333;
        }
        h1 {
            color: #2c3e50;
        }
        ul {
            list-style-type: none;
            padding-left: 0;
        }
        li {
            background: #ffffff;
            margin: 10px 0;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        a {
            text-decoration: none;
            color: #2980b9;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Welcome to Arunima Bollampally's GitHub Portfolio</h1>
    <p>Chemical Engineer by profession and Environmentalist at heart.</p>

    <h2>My Public Projects</h2>
    <ul id="repo-list">Loading repositories...</ul>

    <script>
        fetch("https://api.github.com/users/Arunima-Bollampally/repos")
            .then(response => response.json())
            .then(repos => {
                const list = document.getElementById("repo-list");
                list.innerHTML = "";
                repos.forEach(repo => {
                    const item = document.createElement("li");
                    item.innerHTML = `<a href="${repo.html_url}" target="_blank">${repo.name}</a><p>${repo.description || ''}</p>`;
                    list.appendChild(item);
                });
            })
            .catch(error => {
                document.getElementById("repo-list").innerText = "Failed to load repositories.";
                console.error(error);
            });
    </script>
</body>
</html>
