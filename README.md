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
</html>
