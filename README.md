# xyy
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>轻钢龙骨吊顶构造对比图</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', 'Microsoft YaHei', sans-serif;
        }
        
        body {
            background-color: #f8f9fa;
            color: #333;
            line-height: 1.6;
            padding: 20px;
            max-width: 1400px;
            margin: 0 auto;
        }
        
        .header {
            text-align: center;
            margin-bottom: 30px;
            padding-bottom: 15px;
            border-bottom: 2px solid #3498db;
        }
        
        .header h1 {
            color: #2c3e50;
            font-size: 2.2rem;
            margin-bottom: 8px;
        }
        
        .header p {
            color: #7f8c8d;
            font-size: 1.1rem;
        }
        
        .comparison-container {
            display: flex;
            flex-wrap: wrap;
            gap: 25px;
            margin-bottom: 40px;
        }
        
        .view-section {
            flex: 1;
            min-width: 300px;
            background: white;
            border-radius: 12px;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.08);
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .view-section:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.12);
        }
        
        .section-header {
            background: linear-gradient(to right, #3498db, #2c3e50);
            color: white;
            padding: 18px 25px;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .section-header h2 {
            font-size: 1.5rem;
            font-weight: 600;
        }
        
        .view-content {
            padding: 0;
            height: 500px;
            display: flex;
            flex-direction: column;
        }
        
        #threeD-container {
            height: 100%;
            width: 100%;
            background-color: #f0f7ff;
            border: none;
            flex-grow: 1;
            position: relative;
            overflow: hidden;
        }
        
        .sketchfab-embed-wrapper {
            width: 100%;
            height: 100%;
        }
        
        .sketchfab-embed-wrapper iframe {
            width: 100%;
            height: 100%;
            border: none;
        }
        
        .plane-image-container {
            height: 100%;
            width: 100%;
            display: flex;
            flex-direction: column;
        }
        
        .plane-image {
            height: 85%;
            width: 100%;
            background-color: #f9f9f9;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            position: relative;
        }
        
        .plane-image img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
            display: block;
        }
        
        .image-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0);
            transition: background 0.3s;
        }
        
        .plane-image-container:hover .image-overlay {
            background: rgba(0, 0, 0, 0.05);
        }
        
        .image-zoom {
            position: absolute;
            top: 15px;
            right: 15px;
            background: rgba(255, 255, 255, 0.9);
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            transition: all 0.3s;
            z-index: 10;
        }
        
        .image-zoom:hover {
            background: #3498db;
            color: white;
            transform: scale(1.1);
        }
        
        .legend {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            padding: 15px;
            background: white;
            border-top: 1px solid #eee;
        }
        
        .legend-item {
            display: flex;
            align-items: center;
            font-size: 0.85rem;
        }
        
        .legend-color {
            width: 16px;
            height: 16px;
            margin-right: 8px;
            border-radius: 2px;
        }
        
        .details-section {
            background-color: white;
            border-radius: 12px;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.08);
            padding: 30px;
            margin-bottom: 30px;
        }
        
        .details-header {
            color: #2c3e50;
            margin-bottom: 25px;
            padding-bottom: 15px;
            border-bottom: 2px solid #eee;
            display: flex;
            align-items: center;
        }
        
        .details-header i {
            margin-right: 12px;
            color: #3498db;
        }
        
        .details-content {
            display: flex;
            flex-wrap: wrap;
            gap: 40px;
        }
        
        .materials, .notes {
            flex: 1;
            min-width: 300px;
        }
        
        .materials h3, .notes h3 {
            color: #3498db;
            margin-bottom: 18px;
            display: flex;
            align-items: center;
        }
        
        .materials h3 i, .notes h3 i {
            margin-right: 10px;
        }
        
        .material-list {
            list-style-type: none;
        }
        
        .material-list li {
            padding: 12px 15px;
            margin-bottom: 10px;
            background-color: #f8fafc;
            border-radius: 8px;
            border-left: 4px solid #3498db;
            display: flex;
            justify-content: space-between;
        }
        
        .material-name {
            font-weight: 600;
            color: #2c3e50;
        }
        
        .material-spec {
            color: #7f8c8d;
            font-size: 0.9rem;
        }
        
        .notes-list {
            list-style-type: none;
        }
        
        .notes-list li {
            padding: 12px 15px;
            margin-bottom: 12px;
            background-color: #f0f7ff;
            border-radius: 8px;
            border-left: 4px solid #2ecc71;
            display: flex;
            align-items: flex-start;
        }
        
        .notes-list li i {
            color: #2ecc71;
            margin-right: 12px;
            margin-top: 3px;
        }
        
        .specification {
            background-color: #2c3e50;
            color: white;
            padding: 20px;
            border-radius: 10px;
            margin-top: 20px;
            font-family: monospace;
            line-height: 1.8;
        }
        
        .specification strong {
            color: #3498db;
        }
        
        .footer {
            text-align: center;
            padding: 20px;
            color: #7f8c8d;
            font-size: 0.9rem;
            border-top: 1px solid #eee;
            margin-top: 20px;
        }
        
        /* 模态框样式 */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.9);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }
        
        .modal-content {
            max-width: 90%;
            max-height: 90%;
            position: relative;
        }
        
        .modal-content img {
            width: 100%;
            height: auto;
            border-radius: 5px;
        }
        
        .close-modal {
            position: absolute;
            top: -40px;
            right: 0;
            color: white;
            font-size: 30px;
            cursor: pointer;
        }
        
        @media (max-width: 768px) {
            .comparison-container {
                flex-direction: column;
            }
            
            .view-section {
                min-width: 100%;
            }
            
            .view-content {
                height: 400px;
            }
            
            .details-content {
                flex-direction: column;
            }
            
            .header h1 {
                font-size: 1.8rem;
            }
        }
        
        .loading {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: rgba(255, 255, 255, 0.9);
            z-index: 100;
        }
        
        .spinner {
            width: 50px;
            height: 50px;
            border: 5px solid #f3f3f3;
            border-top: 5px solid #3498db;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body>
    <div class="header">
        <h1><i class="fas fa-drafting-compass"></i> 轻钢龙骨吊顶构造对比图</h1>
        <p>3D模型与平面构造图对比分析 | 包含完整材质与施工注意事项</p>
    </div>
    
    <div class="comparison-container">
        <div class="view-section">
            <div class="section-header">
                <h2><i class="fas fa-cube"></i> 3D 效果图</h2>
                <span class="section-tag">交互式模型</span>
            </div>
            <div class="view-content">
                <div id="threeD-container">
                    <!-- Sketchfab 3D模型嵌入 -->
                    <div class="sketchfab-embed-wrapper">
                        <iframe 
                            title="轻钢龙骨吊顶模型" 
                            frameborder="0" 
                            allowfullscreen 
                            mozallowfullscreen="true" 
                            webkitallowfullscreen="true" 
                            allow="autoplay; fullscreen; xr-spatial-tracking" 
                            xr-spatial-tracking 
                            execution-while-out-of-viewport 
                            execution-while-not-rendered 
                            web-share 
                            src="https://sketchfab.com/models/7080b751e8074178ab6aea6a41e36b76/embed?autospin=1&autostart=1&ui_controls=1&ui_infos=1&ui_stop=1&ui_watermark=0">
                        </iframe>
                    </div>
                </div>
                <div class="legend">
                    <div class="legend-item">
                        <div class="legend-color" style="background-color: #9e9e9e;"></div>
                        <span>丝杆/M8膨胀螺栓</span>
                    </div>
                    <div class="legend-item">
                        <div class="legend-color" style="background-color: #616161;"></div>
                        <span>主龙骨</span>
                    </div>
                    <div class="legend-item">
                        <div class="legend-color" style="background-color: #757575;"></div>
                        <span>副龙骨</span>
                    </div>
                    <div class="legend-item">
                        <div class="legend-color" style="background-color: #ffeb3b;"></div>
                        <span>暗藏灯带</span>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="view-section">
            <div class="section-header">
                <h2><i class="fas fa-drafting-compass"></i> 平面构造图</h2>
                <span class="section-tag">施工示意图</span>
            </div>
            <div class="view-content">
                <div class="plane-image-container">
                    <div class="plane-image">
                        <img src="https://image2url.com/r2/bucket1/images/1767711529066-e76f5725-72b3-4923-aff6-2582dffb6dc8.jpg" alt="轻钢龙骨吊顶平面构造图" id="planeImg">
                        <div class="image-overlay"></div>
                        <div class="image-zoom" id="zoomBtn">
                            <i class="fas fa-search-plus"></i>
                        </div>
                    </div>
                    <div class="legend">
                        <div class="legend-item">
                            <div class="legend-color" style="background-color: #2c3e50;"></div>
                            <span>丝杆固定点</span>
                        </div>
                        <div class="legend-item">
                            <div class="legend-color" style="background-color: #3498db;"></div>
                            <span>主龙骨方向</span>
                        </div>
                        <div class="legend-item">
                            <div class="legend-color" style="background-color: #ff9800;"></div>
                            <span>副龙骨方向</span>
                        </div>
                        <div class="legend-item">
                            <div class="legend-color" style="background-color: #2ecc71;"></div>
                            <span>吊件位置</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <div class="details-section">
        <div class="details-header">
            <i class="fas fa-clipboard-list fa-lg"></i>
            <h2>材料清单与施工注意事项</h2>
        </div>
        
        <div class="details-content">
            <div class="materials">
                <h3><i class="fas fa-boxes"></i> 主要材料清单</h3>
                <ul class="material-list">
                    <li>
                        <span class="material-name">M6螺栓</span>
                        <span class="material-spec">紧固连接</span>
                    </li>
                    <li>
                        <span class="material-name">螺母</span>
                        <span class="material-spec">配合螺栓使用</span>
                    </li>
                    <li>
                        <span class="material-name">垫圈</span>
                        <span class="material-spec">防松、分散压力</span>
                    </li>
                    <li>
                        <span class="material-name">吊件 (60系列)</span>
                        <span class="material-spec">龙骨连接件</span>
                    </li>
                    <li>
                        <span class="material-name">主龙骨 (60系列)</span>
                        <span class="material-spec">@900mm间距</span>
                    </li>
                    <li>
                        <span class="material-name">副龙骨</span>
                        <span class="material-spec">@300mm间距</span>
                    </li>
                    <li>
                        <span class="material-name">M8膨胀螺栓</span>
                        <span class="material-spec">顶部固定</span>
                    </li>
                    <li>
                        <span class="material-name">丝杆</span>
                        <span class="material-spec">M8，吊挂龙骨</span>
                    </li>
                    <li>
                        <span class="material-name">石膏板</span>
                        <span class="material-spec">单层9.5mm + 双层9.5mm</span>
                    </li>
                </ul>
                
                <div class="specification">
                    <strong>详细规格说明：</strong><br>
                    8丝杆 M8膨胀螺栓固定50主龙@900 50副龙@300<br>
                    X600系列轻钢龙骨吊顶<br>
                    单层9.5mm石膏板 + 双层9.5mm石膏板<br>
                    表面处理：满批腻子三度，乳胶漆三度<br>
                    暗藏灯带：LED灯带，色温3000K-4000K可选
                </div>
            </div>
            
            <div class="notes">
                <h3><i class="fas fa-exclamation-triangle"></i> 施工注意事项</h3>
                <ul class="notes-list">
                    <li>
                        <i class="fas fa-check-circle"></i>
                        <div>确保所有膨胀螺栓固定牢固，丝杆垂直度误差不超过3mm</div>
                    </li>
                    <li>
                        <i class="fas fa-check-circle"></i>
                        <div>主龙骨间距严格控制在900mm以内，副龙骨间距控制在300mm以内</div>
                    </li>
                    <li>
                        <i class="fas fa-check-circle"></i>
                        <div>吊件安装必须牢固，与龙骨连接紧密无松动</div>
                    </li>
                    <li>
                        <i class="fas fa-check-circle"></i>
                        <div>灯带预留槽位置准确，确保灯带安装后光线均匀无暗区</div>
                    </li>
                    <li>
                        <i class="fas fa-check-circle"></i>
                        <div>石膏板接缝应错开，板间留3-5mm缝隙，防止开裂</div>
                    </li>
                    <li>
                        <i class="fas fa-check-circle"></i>
                        <div>双层石膏板应错缝安装，上层板接缝不得与下层板接缝重合</div>
                    </li>
                    <li>
                        <i class="fas fa-check-circle"></i>
                        <div>满批腻子三度，每度干透后方可进行下一度施工</div>
                    </li>
                    <li>
                        <i class="fas fa-check-circle"></i>
                        <div>乳胶漆涂刷三度，确保颜色均匀，无流挂、刷痕</div>
                    </li>
                    <li>
                        <i class="fas fa-check-circle"></i>
                        <div>施工前需检查楼板强度，确保能承受吊顶重量</div>
                    </li>
                    <li>
                        <i class="fas fa-check-circle"></i>
                        <div>所有金属部件需做好防锈处理，防止日后生锈</div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
    
    <div class="footer">
        <p>轻钢龙骨吊顶构造对比图 | 设计施工参考图 | 更新时间: 2023年11月</p>
        <p>注：3D模型为交互式展示，可使用鼠标旋转、缩放查看细节；平面图可点击放大查看</p>
    </div>

    <!-- 图片放大模态框 -->
    <div class="modal" id="imageModal">
        <div class="modal-content">
            <span class="close-modal" id="closeModal">&times;</span>
            <img src="https://image2url.com/r2/bucket1/images/1767711529066-e76f5725-72b3-4923-aff6-2582dffb6dc8.jpg" alt="轻钢龙骨吊顶平面构造图（放大）">
        </div>
    </div>

    <script>
        // 添加3D模型加载指示器
        document.addEventListener('DOMContentLoaded', function() {
            const iframe = document.querySelector('#threeD-container iframe');
            const container = document.querySelector('#threeD-container');
            
            // 创建加载指示器
            const loadingDiv = document.createElement('div');
            loadingDiv.className = 'loading';
            loadingDiv.innerHTML = '<div class="spinner"></div>';
            container.appendChild(loadingDiv);
            
            // 当iframe加载完成后移除加载指示器
            iframe.addEventListener('load', function() {
                setTimeout(function() {
                    loadingDiv.style.opacity = '0';
                    loadingDiv.style.transition = 'opacity 0.5s';
                    setTimeout(function() {
                        loadingDiv.remove();
                    }, 500);
                }, 1500); // 稍微延迟一点确保模型开始渲染
            });
            
            // 如果加载失败，显示错误信息
            iframe.addEventListener('error', function() {
                loadingDiv.innerHTML = '<p style="color: #e74c3c;">3D模型加载失败，请检查网络连接</p>';
            });
            
            // 图片加载处理
            const planeImg = document.getElementById('planeImg');
            const planeImageContainer = document.querySelector('.plane-image');
            
            // 创建图片加载指示器
            const imgLoadingDiv = document.createElement('div');
            imgLoadingDiv.className = 'loading';
            imgLoadingDiv.innerHTML = '<div class="spinner"></div>';
            planeImageContainer.appendChild(imgLoadingDiv);
            
            // 图片加载完成后移除加载指示器
            planeImg.addEventListener('load', function() {
                imgLoadingDiv.style.opacity = '0';
                imgLoadingDiv.style.transition = 'opacity 0.5s';
                setTimeout(function() {
                    imgLoadingDiv.remove();
                }, 500);
            });
            
            // 图片加载失败处理
            planeImg.addEventListener('error', function() {
                imgLoadingDiv.innerHTML = '<p style="color: #e74c3c;">平面图加载失败，请检查图片链接</p>';
            });
            
            // 图片放大功能
            const zoomBtn = document.getElementById('zoomBtn');
            const imageModal = document.getElementById('imageModal');
            const closeModal = document.getElementById('closeModal');
            
            zoomBtn.addEventListener('click', function() {
                imageModal.style.display = 'flex';
            });
            
            closeModal.addEventListener('click', function() {
                imageModal.style.display = 'none';
            });
            
            // 点击模态框背景关闭
            imageModal.addEventListener('click', function(e) {
                if (e.target === imageModal) {
                    imageModal.style.display = 'none';
                }
            });
            
            // ESC键关闭模态框
            document.addEventListener('keydown', function(e) {
                if (e.key === 'Escape' && imageModal.style.display === 'flex') {
                    imageModal.style.display = 'none';
                }
            });
        });
    </script>
</body>
</html>
