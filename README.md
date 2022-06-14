<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Danh sách ca sĩ</title>
</head>
<body>
    <h1>Danh sách ca sĩ</h1>
    <?php
    include("config.php");
    $query = "select * from tbl_casi";
    $result = mysqli_query($conn,$query);


    ?>
    <form action="" method="get">
        <table border="1px">
            <tr>
                <th>Mã Ca Sĩ</th>
                <th>Tên Ca Sĩ</th>
                <th>Địa chỉ</th>
                <th>Thao tác</th>
            </tr>
            <?php
                while($dong = mysqli_fetch_array($result)){

            ?>
            <tr>
                <td><?php echo $dong['MaCasi']  ?></td>
                <td><?php echo $dong['TenCasi'] ?></td>
                <td><?php echo $dong['DiaChi'] ?></td>
                <td><a href="sua.php"> Sửa </a>|<a href="xoa.php"> Xóa</a></td>
            </tr>
            <?php
                }
            ?>
        </table>


    </form>

    
</body>
</html>
