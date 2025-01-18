<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no">
    <title>商品购物 - Namo Studio</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
        /* 页面样式 */
        body {
            font-family: 'Roboto', sans-serif;
            background-color: #f9f9f9;
            padding: 0;
        }
        .container {
            margin-top: 30px;
        }
        .product-card {
            margin-bottom: 30px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }
        .product-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-top-left-radius: 8px;
            border-top-right-radius: 8px;
        }
        .product-title {
            font-size: 18px;
            font-weight: bold;
            margin-top: 10px;
        }
        .product-price {
            font-size: 16px;
            color: #ff6f61;
            margin-top: 5px;
        }
        .product-desc {
            font-size: 14px;
            color: #666;
        }
        .btn-cart {
            margin-top: 10px;
        }
        /* logo 样式 */
        header {
            background-color: #ff6f61;
            text-align: center;
            padding: 20px;
        }
        .logo {
            font-size: 24px;
            color: white;
            text-decoration: none;
        }
        /* 详情弹窗样式 */
        .modal-body img {
            width: 100%;
            height: auto;
        }
    </style>
</head>
<body>
    <!-- 页头 -->
    <header>
        <a href="#home" class="logo">Namo Studio</a>
    </header>

    <!-- 商品展示部分 -->
    <div class="container">
        <div class="row">
            <!-- 商品1 -->
            <div class="col-md-4">
                <div class="card product-card">
                    <img src="product1.jpg" class="card-img-top product-img" alt="商品1">
                    <div class="card-body">
                        <h5 class="product-title">创意玩具1</h5>
                        <p class="product-price">￥199</p>
                        <p class="product-desc">这是一款非常有趣的创意玩具，非常适合送给孩子们。</p>
                        <button class="btn btn-primary btn-cart" onclick="addToCart('创意玩具1')">加入购物车</button>
                        <button class="btn btn-info mt-2" onclick="viewDetails('product1', '创意玩具1', '￥199', '这是一款非常有趣的创意玩具，非常适合送给孩子们。', 'product1.jpg')">查看详情</button>
                    </div>
                </div>
            </div>

            <!-- 商品2 -->
            <div class="col-md-4">
                <div class="card product-card">
                    <img src="product2.jpg" class="card-img-top product-img" alt="商品2">
                    <div class="card-body">
                        <h5 class="product-title">创意玩具2</h5>
                        <p class="product-price">￥299</p>
                        <p class="product-desc">这款玩具设计独特，带给你无限的创意灵感。</p>
                        <button class="btn btn-primary btn-cart" onclick="addToCart('创意玩具2')">加入购物车</button>
                        <button class="btn btn-info mt-2" onclick="viewDetails('product2', '创意玩具2', '￥299', '这款玩具设计独特，带给你无限的创意灵感。', 'product2.jpg')">查看详情</button>
                    </div>
                </div>
            </div>

            <!-- 商品3 -->
            <div class="col-md-4">
                <div class="card product-card">
                    <img src="product3.jpg" class="card-img-top product-img" alt="商品3">
                    <div class="card-body">
                        <h5 class="product-title">创意玩具3</h5>
                        <p class="product-price">￥399</p>
                        <p class="product-desc">这款玩具非常适合成年人，帮助放松和释放压力。</p>
                        <button class="btn btn-primary btn-cart" onclick="addToCart('创意玩具3')">加入购物车</button>
                        <button class="btn btn-info mt-2" onclick="viewDetails('product3', '创意玩具3', '￥399', '这款玩具非常适合成年人，帮助放松和释放压力。', 'product3.jpg')">查看详情</button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- 商品详情弹出框 -->
    <div class="modal fade" id="productModal" tabindex="-1" aria-labelledby="productModalLabel" aria-hidden="true">
        <div class="modal-dialog modal-lg">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="productModalLabel">商品详情</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body">
                    <img id="productImage" src="" alt="商品图片">
                    <h4 id="productName"></h4>
                    <p id="productPrice"></p>
                    <p id="productDesc"></p>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">关闭</button>
                </div>
            </div>
        </div>
    </div>

    <!-- 脚本 -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/js/bootstrap.bundle.min.js"></script>
    <script>
        function addToCart(productName) {
            alert(productName + ' 已加入购物车');
        }

        function viewDetails(id, name, price, desc, img) {
            document.getElementById("productModalLabel").innerText = name + " - 详情";
            document.getElementById("productImage").src = img;
            document.getElementById("productName").innerText = name;
            document.getElementById("productPrice").innerText = "价格：" + price;
            document.getElementById("productDesc").innerText = desc;
            var modal = new bootstrap.Modal(document.getElementById('productModal'));
            modal.show();
        }
    </script>
</body>
</html>
