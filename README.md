<h1>docker-for-laravel Support 6, 7, 8, 9</h2>
<h3>Stack</h3>
<ul>
    <li>nginx</li>
    <li>php8.0-fpm</li>
    <li>mysql</li>
    <li>phpmyadmin</li>
</ul>
<h3>วิธีใช้งาน</h3>
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
    <li>แก้ไขส่วนของ Connect database ตาม flie <code>docker-compose.yml</code> ตรง  mysql8-service ให้เรียบร้อย ใน file <code>.env</code></li>
    <li>เปิด Browser ใส่ url <code>http://localhost:8020</code> อีกครั้ง</li>
</ol>
<span>enjoy!! &#128008;</span>
