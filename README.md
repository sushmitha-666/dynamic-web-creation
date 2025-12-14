<!DOCTYPE html>
<html>
<head>
  <title>DT Internship Programs</title>

  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f2f2f2;
      text-align: center;
    }

    button {
      padding: 8px 15px;
      margin: 5px;
      cursor: pointer;
    }

    .card {
      background: white;
      margin: 10px auto;
      padding: 15px;
      width: 300px;
      border-radius: 5px;
    }

    .open {
      color: green;
      font-weight: bold;
    }

    .closed {
      color: red;
      font-weight: bold;
    }
  </style>
</head>

<body>

  <h1>DT Internship Programs</h1>

  <button onclick="showAll()">All</button>
  <button onclick="showOpen()">Open</button>
  <button onclick="showClosed()">Closed</button>

  <div id="list"></div>

  <script>
    const internships = [
      { name: "Frontend Intern", status: "Open" },
      { name: "Backend Intern", status: "Closed" },
      { name: "Research Intern", status: "Open" }
    ];

    const list = document.getElementById("list");

    function display(data) {
      list.innerHTML = "";
      data.forEach(item => {
        list.innerHTML += `
          <div class="card">
            <h3>${item.name}</h3>
            <p class="${item.status.toLowerCase()}">${item.status}</p>
          </div>
        `;
      });
    }

    function showAll() {
      display(internships);
    }

    function showOpen() {
      display(internships.filter(i => i.status === "Open"));
    }

    function showClosed() {
      display(internships.filter(i => i.status === "Closed"));
    }

    showAll();
  </script>

</body>
</html>
