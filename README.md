<h1>docker-for-laravel</h2>
<h2>วิธีใช้งาน</h2>
<ol>
    <li>เปิด vscode และ ทำการสร้าง folder ของ project</li>
    <li>เปิด Terminal ใน vscode</li>
    <li><code>git clone https://github.com/adcident12/docker-for-laravel.git</code></li>
    <li><code>cd docker-for-laravel</code></li>
    <li><code>docker-compose up -d --build</code></li>
    <li>รอจนเสร็จ</li>
    <li>ลองสร้าง folder ใน app ชื่อ public และ เพิ่ม file index.php ภายในให้แสดง <code>phpinfo();</code></li>
    <li>เปิด Browser ใส่ url <code>http://localhost:8020</code></li>
    <li>หลังจากนั้นก็ ลบ folder app ออก แล้วทำการติดตั้งตัว laravel <code>composer create-project laravel/laravel app</code></li>
    <li>แก้ไขส่วนของ connect database ตาม flie <code>docker-compose.yml</code> ตรง  mysql8-service ให้เรียบร้อย ใน file <code>.env</code></li>
    <li>เปิด Browser ใส่ url <code>http://localhost:8020</code> อีกครั้ง</li>
</ol>
<span>enjoy!! &#128008;</span>
