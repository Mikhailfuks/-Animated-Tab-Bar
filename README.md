<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animated Tab Bar</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }

        .tab-bar {
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: #f2f2f2;
            padding: 10px 0;
            margin-bottom: 20px;
        }

        .tab {
            padding: 10px 20px;
            margin: 0 5px;
            border-bottom: 3px solid transparent;
            cursor: pointer;
            transition: border-bottom 0.3s ease;
        }

        .tab.active {
            border-bottom-color: #4CAF50; /* Active tab color */
        }

        .tab-content {
            border: 1px solid #ddd;
            padding: 20px;
            display: none;
        }

        .tab-content.active {
            display: block;
        }
    </style>
</head>
<body>

    <div class="tab-bar">
        <div class="tab active" data-target="tab1">Tab 1</div>
        <div class="tab" data-target="tab2">Tab 2</div>
        <div class="tab" data-target="tab3">Tab 3</div>
    </div>

    <div class="tab-content active" id="tab1">
        <h2>Content for Tab 1</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
    </div>

    <div class="tab-content" id="tab2">
        <h2>Content for Tab 2</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
    </div>

    <div class="tab-content" id="tab3">
        <h2>Content for Tab 3</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
    </div>

    <script>
        const tabs = document.querySelectorAll('.tab');
        const tabContents = document.querySelectorAll('.tab-content');

        tabs.forEach(tab => {
            tab.addEventListener('click', () => {
                // Remove active class from all tabs and tab contents
                tabs.forEach(t => t.classList.remove('active'));
                tabContents.forEach(content => content.classList.remove('active'));

                // Add active class to the clicked tab and its corresponding content
                tab.classList.add('active');
                const targetId = tab.dataset.target;
                document.getElementById(targetId).classList.add('active');
            });
        });
    </script>

</body>
</html>
