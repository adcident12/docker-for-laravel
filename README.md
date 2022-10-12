<h1>docker-for-laravel Recommend 8, 9</h2>
<h3>Stack</h3>
<ul>
    <li>nginx</li>
    <li>php8.0-fpm</li>
    <li>mysql</li>
    <li>phpmyadmin</li>
</ul>
<h3>How to use</h3>
<ol>
    <li>เปิด Vscode และ ทำการสร้าง folder ของ project</li>
    <li>เปิด Terminal ใน vscode</li>
    <li><code>git clone https://github.com/adcident12/docker-for-laravel.git</code></li>
    <li><code>cd docker-for-laravel</code></li>
    <li><code>docker-compose up -d --build</code></li>
    <li>รอจนเสร็จ</li>
    <li>ลองสร้าง Folder ใน app ชื่อ public และ เพิ่ม file index.php ภายในให้แสดง <code>phpinfo();</code></li>
    <li>เปิด Browser ใส่ url <code>http://localhost:8020</code></li>
    <li>หลังจากนั้นก็ ลบ Folder app ออก แล้วทำการติดตั้งตัว laravel <code>composer create-project laravel/laravel app</code></li>
    <li>แก้ไขส่วนของ Connect database ตาม flie <code>docker-compose.yml</code> ตรง  mysql8-service ให้เรียบร้อย ใน file <code>.env</code><div><code>DB_HOST=mysql8-container</code></div><div><code>DB_PORT=3306</code></div><div><code>DB_DATABASE=laravel</code></div><div><code>DB_USERNAME=root</code></div><div><code>DB_PASSWORD=secret</code></div></li>
    <li>เปิด Browser ใส่ url <code>http://localhost:8020</code> อีกครั้ง</li>
    <li>ส่วน phpmyadmin จะอยู่ที่ <code>url: http://localhost:8021</code><div><code>server: mysql8-service</code></div><div><code>username: root</code></div><div><code>password: secret</code></div></li>
</ol>
<h3>How to change the maximum file size</h3>
<ol>
    <li><code>docker ps</code> และ copy ในส่วนของ NAMES ของ IMAGE ที่เป็น php service ตามเอกสาร NAMES คือ (php80-container)</li>
    <li><code>docker exec -it {NAMES} bash</code> ตามเอกสาร NAMES คือ (php80-container)</li>
    <li><code>cd /usr/local/etc/php/conf.d</code></li>
    <li><code>nano uploads.ini</code> copy ด้านล่างวาง
    <div><code>file_uploads = On</code></div>
    <div><code>memory_limit = 500M</code></div>
    <div><code>upload_max_filesize = 100M</code></div>
    <div><code>post_max_size = 100M</code></div>
    <div><code>max_execution_time = 600</code></div>
    <div><code>max_file_uploads = 50000</code></div>
    <div><code>max_execution_time = 5000</code></div>
    <div><code>max_input_time = 5000</code></div>
    </li>
    <li>ใส่ ตัวเลขตามต้องการ และ save (ctrl x y enter)</li>
    <li><code>exit</code></li>
    <li><code>docker-compose restart</code></li>
</ol>
<h3>How to fix Error Connection refused</h3>
<ol>
    <li>ดู ip ของ container ต่างๆ <code>docker inspect -f '{{.Name}} - {{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' $(docker ps -aq)
</code></li>
    <li>เอา ip ของ mysql8-container ใส่แทน DB_HOST=127.0.0.1 ใน file <code>.env</code></li>
</ol>
<span>enjoy!! &#128008;</span>
<div>Ref. https://github.com/GaryClarke/nginx-php7.4-mysql8-node-docker-network</div>
<div>Ref. https://sidshome.wordpress.com/2020/06/05/how-to-change-the-maximum-file-size-you-can-upload-to-wordpress-on-nginx-w-php-fpm/</div>
<div>Ref. https://laracasts.com/discuss/channels/laravel/dock-laravel-sqlstatehy000-2002-connection-refused</div>

