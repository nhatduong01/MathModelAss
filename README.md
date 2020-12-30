# MathModelAss
A math model assignment

# Hướng dẫn viết python function

## Cơ bản
Giả sử ta có một công thức tính MC_xy như sau:

![MC_{xy}=\dfrac{A*c*d}{B}](https://latex.codecogs.com/svg.latex?MC_{xy}=\dfrac{A*c*d}{B})

Ta sẽ viết python function theo format sau:

```python
"""
Đây là những thông số của công thức, khi ghi công thức, một số constant như hệ số nhiệt tạo ra bởi máy, ...
có thể tìm trong sách thì mọi người nhớ note vào trực tiếp input_dict của mình nha. Để tiện khi chúng ta
gáp công thức lại. Còn những thông số không tìm được trong sách hay số từ dữ liệu thật thì để
dưới dạng variable.

Ở đây, ta có A,d, B đều là constant tìm được trong sách. Riêng c là variable. 
Trong quá trình lấy từ dữ liệu thật, ta thay variable_c = [dữ liệu thật].
Trong trường hợp ở đây thì dữ liệu thật của c là 10
"""

variable_c = 10

# Khi viết tuple giống như vầy thì mọi người nhớ chú thích thứ tự nha.
# Ví dụ như: (A, c, d, B)
input_tuple = (5, variable_c, 1.2, 15)

# function body
def mc_xy(my_tuple):
  # Lúc extract ra thì theo đúng thứ tự mà extract thôi
  A, c, d, B = my_tuple
  
  result = (A * c * d) / B
  return result
  
# call function

val_mc_xy = mc_xy(input_tuple) #=> 4.0
```

## Hàm python gọi hàm python khác
Lấy ví dụ trên, trong trường hợp A không phải là số mà là một hàm phụ thuộc vào các biến x,y,z...

```python
# order: (c, d, B, x, y, z)
input_tuple = (10, 1.2, 15, 1.6, 2.5, -2)

def funcA(my_tuple):
  x, y, z = my_tuple
  return x*y / z
  
def mc_xy(my_tuple):
  c, d, B, x, y, z = my_tuple
  val_A = funcA((x,y,z))
  result = (val_A * c * d) / B
  return result 
  
val_mc_xy = mc_xy(input_tuple)
```

# Cách commit lên github
- Fork repo này => Mỗi người sẽ có 1 bản copy của repo này trong github.

- Download cái copy về máy làm việc => Làm xong thì push lên copy.

- Nếu cảm thấy ổn áp rồi thì Pull Request(PR). Rồi tiếp tục làm việc.

- Mỗi PR sẽ được assign cho một người trong nhóm làm reviewer. Mỗi thành viên trong nhóm ngoài công thức của mình, cũng sẽ được biết thêm về công thức của người khác. Và chỉ có reviewer mới được quyền merge vào repo.

## Lưu ý
- Tạo file python, sửa file chỉ trong folder đã được chỉ định tên để tránh conflict mất thời gian của nhóm

- Khi viết description cho PR thì phải ghi rõ ràng công thức mình làm là gì. Có những biến nào là variable, biến nào là const. Công thức của mình đã hoàn thành đến mức nào.

- Trong trường hợp muốn thử nghiệm một ý tưởng mới trong code nhưng không đảm bảo về tính an toàn hay khả thi, tạo một branch trong repo này và copy của repo này
(đặt tên tuỳ ý nhưng đừng gây nhầm lẫn khi có quá nhiều branch được tạo). Trong branch đó, tạo một file `GUIDE.md` ghi lại lý do thực hiện ý tưởng và phương pháp. 
Rồi tiến hành làm. Sau khi làm xong trên branch của copy repo của mình, PR vào đúng branch cùng tên trên repo này.

- Trong quá trình làm:
  + Nếu có điều gì không chắc thì raise lên trong group messenger.
  + Nếu có issues thì ghi thêm trên trello để tiện follow.
  + Nếu có ý tưởng mới tạo branch thì raise lên trên messenger để mọi người theo dõi.
  
# Chúc mọi người làm việc hiệu quả và vui vẻ
