<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: black;
            color: black;
            text-align: center;
            margin: 0;
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        pre {
            font-size: 20px;
            color: green;
        }
    </style>
</head>
<body>
    <h1>Giáng Sinh Vui Vẻ 💕</h1>
    <pre id="tree"></pre>

    <script>
        function getRandomColor() {
            const colors = ['#FF0000', '#FFFF00', '#0000FF'];
            return colors[Math.floor(Math.random() * colors.length)];
        }

        function createXmasTree(height) {
            let tree = '';
            for (let i = 0; i < height; i++) {
                const spaces = ' '.repeat(height - i - 1);
                let chars = '';
                for (let j = 0; j < (2 * i + 1); j++) {
                    if (Math.random() < 0.1) {
                        chars += `<span style="color: ${getRandomColor()}">*</span>`;
                    } else {
                        chars += '<span style="color: green;">*</span>';
                    }
                }
                tree += spaces + chars + spaces + '\n';
            }
            const trunkSpaces = ' '.repeat(height - 1);
            tree += trunkSpaces + '<span style="color: brown;">mWm</span>' + trunkSpaces + '\n';
            tree += trunkSpaces + '<span style="color: brown;">mWm</span>' + trunkSpaces + '\n';
            tree += trunkSpaces + '<span style="color: brown;">mWm</span>' + trunkSpaces + '\n';
            tree += trunkSpaces + '<span style="color: brown;">mWm</span>' + trunkSpaces;

            return tree;
        }

        function displayTree() {
            const treeElement = document.getElementById('tree');
            treeElement.innerHTML = createXmasTree(16);
        }

        // Cập nhật cây thông mỗi 200ms
        setInterval(displayTree, 200);
    </script>
</body>
</html>
