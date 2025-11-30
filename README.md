# Technology-project-P
CODE:
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🐍 Sổ Tay Học Python & HTML</title>
    
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f7f6;
            color: #333;
        }

        header {
            background-color: #4868f4; /* Màu xanh đậm */
            color: white;
            padding: 20px 0;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }

        .container {
            display: flex; /* Bật layout 3 cột */
            max-width: 1400px; /* Tăng chiều rộng để chứa 3 cột */
            margin: 30px auto;
            padding: 0 20px;
            gap: 20px; /* Khoảng cách giữa các khu vực */
        }

        /* Định dạng cho các khu vực */
        .planner-section, .lesson-section {
            background-color: white;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        /* --- KẾ HOẠCH (PLANNER) --- */
        .planner-section {
            flex: 0.8; /* Cho khu vực Kế hoạch hẹp hơn */
        }
        
        .planner-section h2 {
            color: #007bff;
        }

        /* Cấu trúc nhập liệu mới */
        .input-group-planner {
            display: flex;
            flex-direction: column; 
            margin-bottom: 20px;
            gap: 10px;
        }

        .input-row {
            display: flex;
            gap: 5px;
        }

        #new-task {
            flex-grow: 1;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 10px; 
        }

        #new-task-datetime {
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 10px;
            flex-basis: 150px; 
            color: #555;
        }

        .add-button {
            padding: 10px 15px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .add-button:hover {
            background-color: #0056b3;
        }

        .task-list {
            list-style: none;
            padding: 0;
        }

        .task {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 10px;
            margin-bottom: 8px;
            background-color: #e9ecef;
            border-left: 5px solid #007bff;
            border-radius: 5px;
            transition: background-color 0.3s;
        }
        
        .task-details {
            display: flex;
            flex-direction: column;
            flex-grow: 1;
        }

        .task-title {
            font-weight: bold;
            padding-right: 10px;
        }

        .task-deadline {
            font-size: 0.85em;
            color: #888;
            margin-top: 2px;
        }

        .task-actions {
            display: flex;
            gap: 5px;
            margin-left: 10px;
        }

        .completed {
            border-left: 5px solid #4CAF50;
            background-color: #e6ffed; /* Màu nền nhạt hơn khi hoàn thành */
        }
        
        .completed .task-title {
            text-decoration: line-through;
            opacity: 0.6;
        }

        .complete-button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 5px 10px;
            border-radius: 3px;
            cursor: pointer;
            font-size: 12px;
            transition: background-color 0.3s;
        }

        .complete-button:hover {
            background-color: #45a049;
        }

        .delete-button {
            background-color: #dc3545;
            color: white;
            border: none;
            padding: 5px 10px;
            border-radius: 3px;
            cursor: pointer;
            font-size: 12px;
            transition: background-color 0.3s;
        }

        /* --- BÀI HỌC (LESSONS - Cân bằng 2 cột bài học) --- */
        .lesson-section {
            flex: 1; 
            min-width: 300px;
        }
        
        #python-lessons h2 {
            color: #3279a8; /* Màu Python */
        }
        #html-lessons h2 {
            color: #E34C26; /* Màu cam đặc trưng của HTML */
        }

        .lesson-item {
            border: 1px solid #ddd;
            border-radius: 8px;
            margin-bottom: 10px;
            overflow: hidden;
        }

        .lesson-header {
            background-color: #f8f8f8;
            padding: 15px;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-weight: bold;
            color: #3279a8; /* Mặc định màu Python */
            border-bottom: 1px solid #ddd;
        }
        
        #html-lessons .lesson-header {
            color: #E34C26; 
        }

        .lesson-content {
            padding: 15px;
            display: none; 
            background-color: white;
        }

        .icon {
            color: #272822ee;
            font-size: 1.2em;
            transition: transform 0.3s;
        }

        .lesson-item.active .icon {
            transform: rotate(90deg);
        }

        pre {
            background-color: #272822;
            color: #f8f8f2;
            padding: 15px;
            border-radius: 5px;
            overflow-x: auto;
        }

        code {
            font-family: 'Consolas', 'Courier New', monospace;
        }

        #happy {
            position: fixed;
            bottom: 0px;
            right: 0px;
            border-radius: 50px;
            border-color: #272822;
            border-width: 100px;
        }

        #LINK {
            position: relative;
            left: -105px;
            top: 95px;
        }

        #END {
            position: relative;
            left: 500px;
            top: 55px;
        }

        #END1 {
            position: relative;
            left: 285px;
            top: 75px;
        }

        #END2 {
            position: relative;
            left: 155px;
            top: 115px;
        }

        #END3 {
            position: relative;
            left: 25px;
            top: 135px;
        }

    </style>
</head>
<body>

    <header>
        <h1>🐍 Sổ Tay Học Python & HTML Cá Nhân</h1>
        <h4>Võ Đặng Gia Hưng và Trịnh Minh Khang :3</h4>
    </header>

    <main class="container">
        <section class="planner-section">
            <h2>📝 Kế Hoạch Học Tập</h2>
            <div class="input-group-planner">
                <input type="text" id="new-task" placeholder="Thêm bài tập/mục tiêu mới...">
                <div class="input-row">
                    <input type="datetime-local" id="new-task-datetime">
                    <button onclick="addTask()" class="add-button">Thêm</button>
                </div>
            </div>
            <ul id="task-list" class="task-list">
                </ul>
        </section>

        <section class="lesson-section" id="python-lessons">
            <h2>📚 Bài Học Python</h2>
            
            <div class="lesson-item">
                <div class="lesson-header">
                    <span>1. Biến (Variables) và Kiểu dữ liệu</span>
                    <span class="icon">▶</span>
                </div>
                <div class="lesson-content">
                    <p>Trong Python, bạn không cần khai báo kiểu dữ liệu. Chỉ cần gán giá trị!</p>
                    <pre><code># Ví dụ về Biến
ten = "Alice"           # str
tuoi = 30               # int
la_sinh_vien = True     # bool</code></pre>
                </div>
            </div>
            <div class="lesson-item">
                <div class="lesson-header">
                    <span>2. Cấu trúc Điều kiện (if/elif/else)</span>
                    <span class="icon">▶</span>
                </div>
                <div class="lesson-content">
                    <p>Sử dụng **khoảng trắng** (indentation) để xác định khối code.</p>
                    <pre><code># Ví dụ về Cấu trúc Điều kiện
diem = 8
if diem >= 9:
    print("Xuất sắc")
elif diem >= 7:
    print("Khá")
else:
    print("Cần cố gắng")</code></pre>
                </div>
            </div>
            <div class="lesson-item">
                <div class="lesson-header">
                    <span>3. Vòng lặp For và List</span>
                    <span class="icon">▶</span>
                </div>
                <div class="lesson-content">
                    <p>Thường dùng để lặp qua một chuỗi các phần tử (list, string, range).</p>
                    <pre><code># Ví dụ về Vòng lặp For
danh_sach = ["Táo", "Cam", "Chuối"]
for trai_cay in danh_sach:
    print(trai_cay)</code></pre>
                </div>
            </div>
            <div class="lesson-item">
                <div class="lesson-header">
                    <span>4. Hàm (Functions) - Khái niệm cơ bản</span>
                    <span class="icon">▶</span>
                </div>
                <div class="lesson-content">
                    <p>Hàm giúp tổ chức code, tái sử dụng và làm cho chương trình dễ đọc hơn. Được định nghĩa bằng từ khóa **`def`**.</p>
                    <pre><code># Ví dụ về Hàm đơn giản
def chao_mung(ten):
    return f"Xin chào, {ten}!"

print(chao_mung("Người học"))</code></pre>
                </div>
            </div>
        </section>
        
        <section class="lesson-section" id="html-lessons">
            <h2>🧱 Bài Học HTML</h2>

            <div class="lesson-item">
                <div class="lesson-header">
                    <span>1. Cấu trúc Tài liệu HTML</span>
                    <span class="icon">▶</span>
                </div>
                <div class="lesson-content">
                    <p>Mọi tài liệu HTML bắt đầu với `<!DOCTYPE html>` và được bao bọc bởi thẻ `<html>`.</p>
                    <pre><code>&lt;!DOCTYPE html&gt;
&lt;html lang="vi"&gt;
&lt;head&gt;
    &lt;title&gt;Tiêu đề trang&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;
    &lt;h1&gt;Nội dung ở đây&lt;/h1&gt;
&lt;/body&gt;
&lt;/html&gt;</code></pre>
                </div>
            </div>
            
            <div class="lesson-item">
                <div class="lesson-header">
                    <span>2. Thẻ Tiêu đề (Headings)</span>
                    <span class="icon">▶</span>
                </div>
                <div class="lesson-content">
                    <p>Sử dụng các thẻ từ `<h1>` (quan trọng nhất) đến `<h6>` (ít quan trọng nhất) để tạo cấu trúc nội dung.</p>
                    <pre><code>&lt;h1&gt;Tiêu đề Cấp 1&lt;/h1&gt;
&lt;p&gt;Đoạn văn bản đầu tiên.&lt;/p&gt;
&lt;h3&gt;Tiêu đề Cấp 3&lt;/h3&gt;</code></pre>
                </div>
            </div>

            <div class="lesson-item">
                <div class="lesson-header">
                    <span>3. Liên kết (&lt;a&gt;) và Hình ảnh (&lt;img&gt;)</span>
                    <span class="icon">▶</span>
                </div>
                <div class="lesson-content">
                    <p>Thẻ `&lt;a&gt;` tạo liên kết. Thẻ `&lt;img&gt;` chèn hình ảnh (là thẻ tự đóng).</p>
                    <pre><code>&lt;a href="https://google.com" target="_blank"&gt;Đến Google&lt;/a&gt;

&lt;img src="path/to/image.jpg" alt="Mô tả hình ảnh" width="200"&gt;</code></pre>
                </div>
            </div>

            <div class="lesson-item">
                <div class="lesson-header">
                    <span>4. Danh sách (List)</span>
                    <span class="icon">▶</span>
                </div>
                <div class="lesson-content">
                    <p>Sử dụng `&lt;ul&gt;` cho danh sách không có thứ tự và `&lt;ol&gt;` cho danh sách có thứ tự. Mỗi mục là một thẻ `&lt;li&gt;`.</p>
                    <pre><code>&lt;ul&gt;
    &lt;li&gt;Mục 1&lt;/li&gt;
    &lt;li&gt;Mục 2&lt;/li&gt;
&lt;/ul&gt;</code></pre>
                </div>
            </div>

        </section>
    </main>
        
        <hr>
        <img  width = "220" height = "200" id="happy" src = "ve-meme-cute.jpg" alt="Ảnh meme">
        <h7 id = "END">Võ Đặng Gia Hưng & Trịnh Minh Khang</h7>
        <h7 id = "END1">Dự án của tụi mình</h7>
        <h7 id = "END2">Project ICT 5A2</h7>
        <h7 id = "END3">Cảm ơn mọi người:P</h7>
        <a id = "LINK" href = "https://www.canva.com/design/DAG598VNFTs/ZW0Zn7Zy7Qo0EDnmCWaQDg/edit">LINK CANVA</a>

    <script>
        document.addEventListener('DOMContentLoaded', (event) => {
            initTasks(); 
            initLessons(); 
        });
        
        // --- CHỨC NĂNG BÀI HỌC (LESSONS) ---

        /**
         * Gắn sự kiện click cho tất cả các tiêu đề bài học (cả Python và HTML)
         */
        function initLessons() {
            const lessonHeaders = document.querySelectorAll('.lesson-header');
            lessonHeaders.forEach(header => {
                header.addEventListener('click', toggleLessonContent);
            });
        }

        /**
         * Chức năng ẩn/hiện nội dung bài học
         */
        function toggleLessonContent(event) {
            const lessonItem = event.target.closest('.lesson-item');
            const content = lessonItem.querySelector('.lesson-content');

            lessonItem.classList.toggle('active');

            if (content.style.display === "block") {
                content.style.display = "none";
            } else {
                content.style.display = "block";
            }
        }


        // --- CHỨC NĂNG KẾ HOẠCH (PLANNER) ---

        /**
         * Hàm chuyển đổi định dạng datetime-local sang chuỗi ngày/giờ thân thiện
         * @param {string} isoString - Chuỗi định dạng yyyy-MM-ddThh:mm
         * @returns {string} Chuỗi hiển thị (ví dụ: 10:30, 20/12/2025)
         */
        function formatDeadline(isoString) {
            if (!isoString) return 'Không có mốc giờ';
            
            try {
                const date = new Date(isoString);
                
                // Lấy ngày, tháng, năm
                const day = String(date.getDate()).padStart(2, '0');
                const month = String(date.getMonth() + 1).padStart(2, '0');
                const year = date.getFullYear();

                // Lấy giờ, phút
                const hours = String(date.getHours()).padStart(2, '0');
                const minutes = String(date.getMinutes()).padStart(2, '0');

                return `Mốc giờ: ${hours}:${minutes}, ${day}/${month}/${year}`;
            } catch (e) {
                return 'Mốc giờ không hợp lệ';
            }
        }

        /**
         * Tạo phần tử li (task item)
         * @param {string} text - Nội dung công việc
         * @param {string} deadline - Mốc thời gian (datetime-local format)
         */
        function createTaskElement(text, deadline) {
            const listItem = document.createElement('li');
            listItem.classList.add('task');
            
            // 1. Task Details (Title and Deadline)
            const detailsDiv = document.createElement('div');
            detailsDiv.classList.add('task-details');

            const titleSpan = document.createElement('span');
            titleSpan.classList.add('task-title');
            titleSpan.textContent = text;
            detailsDiv.appendChild(titleSpan);

            const deadlineSpan = document.createElement('span');
            deadlineSpan.classList.add('task-deadline');
            deadlineSpan.textContent = formatDeadline(deadline);
            detailsDiv.appendChild(deadlineSpan);

            // 2. Action Buttons
            const actionsDiv = document.createElement('div');
            actionsDiv.classList.add('task-actions');
            
            const completeButton = document.createElement('button');
            completeButton.classList.add('complete-button');
            completeButton.textContent = 'Hoàn thành';
            completeButton.addEventListener('click', toggleComplete);

            const deleteButton = document.createElement('button');
            deleteButton.classList.add('delete-button');
            deleteButton.textContent = 'Xóa';
            deleteButton.addEventListener('click', deleteTask);
            
            actionsDiv.appendChild(completeButton);
            actionsDiv.appendChild(deleteButton);
            
            listItem.appendChild(detailsDiv);
            listItem.appendChild(actionsDiv);
            
            return listItem;
        }

        function initTasks() {
            const taskList = document.getElementById('task-list');
            
            // Sử dụng mốc thời gian giả định trong tương lai (Ví dụ: 2025-12-15T10:00)
            const today = new Date();
            const tomorrow = new Date(today);
            tomorrow.setDate(today.getDate() + 1);
            const tomorrowString = tomorrow.toISOString().substring(0, 16); 
            
            const initialTasks = [
                { text: "Học cú pháp cơ bản Python", deadline: tomorrowString },
                { text: "Xem Bài học 1: Cấu trúc HTML", deadline: '' }, // Không có deadline
                { text: "Hoàn thành dự án 'Máy tính đơn giản'", deadline: '2025-12-31T23:59' }
            ];

            initialTasks.forEach(task => {
                taskList.appendChild(createTaskElement(task.text, task.deadline));
            });
        }
        
        function addTask() {
            const taskInput = document.getElementById('new-task');
            const datetimeInput = document.getElementById('new-task-datetime');
            const taskText = taskInput.value.trim();
            const taskDeadline = datetimeInput.value;

            if (taskText === "") {
                alert("Nhập nội dung kế hoạch đi bro! :P");
                return;
            }

            const taskList = document.getElementById('task-list');
            
            const newListItem = createTaskElement(taskText, taskDeadline);
            taskList.prepend(newListItem); // Thêm vào đầu danh sách

            taskInput.value = '';
            datetimeInput.value = '';
        }

        function toggleComplete(event) {
            // Lấy phần tử li cha gần nhất
            const taskItem = event.target.closest('.task'); 
            taskItem.classList.toggle('completed');
            
            const taskList = document.getElementById('task-list');

            // Di chuyển task hoàn thành xuống cuối danh sách hoặc lên đầu nếu chưa hoàn thành
            if (taskItem.classList.contains('completed')) {
                taskList.appendChild(taskItem);
                event.target.textContent = 'Chưa xong';
                event.target.style.backgroundColor = '#ffc107'; // Màu vàng khi hoàn thành
            } else {
                taskList.prepend(taskItem);
                event.target.textContent = 'Hoàn thành';
                event.target.style.backgroundColor = '#4CAF50'; // Màu xanh lá khi chưa hoàn thành
            }
        }
        
        function deleteTask(event) {
            const taskItem = event.target.closest('.task');
            if (taskItem) {
                taskItem.remove();
            }
        }
    </script>
</body>
</html>
