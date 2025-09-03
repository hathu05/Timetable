<!-- index.html -->
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <title>Thời Khóa Biểu Sinh Viên</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>📅 Thời Khóa Biểu Sinh Viên</h1>
  <div class="table-container">
    <table id="timetable">
      <thead>
        <tr>
          <th>Tiết / Thứ</th>
          <th>Thứ 2</th>
          <th>Thứ 3</th>
          <th>Thứ 4</th>
          <th>Thứ 5</th>
          <th>Thứ 6</th>
          <th>Thứ 7</th>
          <th>CN</th>
        </tr>
      </thead>
      <tbody>
        <!-- 6 tiết mẫu, bạn có thể tăng thêm -->
        <script>
          for (let i = 1; i <= 6; i++) {
            document.write(`<tr>
              <td>Tiết ${i}</td>
              <td contenteditable="true" data-day="2" data-period="${i}"></td>
              <td contenteditable="true" data-day="3" data-period="${i}"></td>
              <td contenteditable="true" data-day="4" data-period="${i}"></td>
              <td contenteditable="true" data-day="5" data-period="${i}"></td>
              <td contenteditable="true" data-day="6" data-period="${i}"></td>
              <td contenteditable="true" data-day="7" data-period="${i}"></td>
              <td contenteditable="true" data-day="8" data-period="${i}"></td>
            </tr>`);
          }
        </script>
      </tbody>
    </table>
  </div>

  <button id="saveBtn">💾 Lưu thời khóa biểu</button>
  <button id="clearBtn">🗑 Xóa hết</button>

  <script src="script.js"></script>
</body>
</html>/* style.css */
body {
  font-family: Arial, sans-serif;
  text-align: center;
  background: #f5f7fa;
  padding: 20px;
}

h1 {
  color: #333;
}

.table-container {
  overflow-x: auto;
  margin: 20px auto;
  max-width: 90%;
}

table {
  border-collapse: collapse;
  width: 100%;
  background: white;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

th, td {
  border: 1px solid #ccc;
  padding: 10px;
  min-width: 100px;
}

th {
  background: #4CAF50;
  color: white;
}

td[contenteditable="true"] {
  cursor: text;
}

button {
  margin: 10px;
  padding: 10px 20px;
  font-size: 16px;
  border: none;
  border-radius: 6px;
  cursor: pointer;
}

#saveBtn {
  background: #4CAF50;
  color: white;
}

#clearBtn {
  background: #e74c3c;
  color: white;
}// script.js
document.addEventListener("DOMContentLoaded", () => {
  const cells = document.querySelectorAll("td[contenteditable='true']");
  const saveBtn = document.getElementById("saveBtn");
  const clearBtn = document.getElementById("clearBtn");

  // Load dữ liệu từ LocalStorage
  cells.forEach(cell => {
    const key = `${cell.dataset.day}-${cell.dataset.period}`;
    cell.textContent = localStorage.getItem(key) || "";
  });

  // Lưu dữ liệu
  saveBtn.addEventListener("click", () => {
    cells.forEach(cell => {
      const key = `${cell.dataset.day}-${cell.dataset.period}`;
      localStorage.setItem(key, cell.textContent);
    });
    alert("✅ Đã lưu thời khóa biểu!");
  });

  // Xóa dữ liệu
  clearBtn.addEventListener("click", () => {
    if (confirm("Bạn có chắc muốn xóa toàn bộ thời khóa biểu?")) {
      cells.forEach(cell => {
        const key = `${cell.dataset.day}-${cell.dataset.period}`;
        localStorage.removeItem(key);
        cell.textContent = "";
      });
    }
  });
});  # Timetable
