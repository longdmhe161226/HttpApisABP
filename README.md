# HttpApisABP
## Create HttpAPIs
- *Api được tạo trong Controller của project .HttpApi.Host*
- *Thông thường thì các ApiController được kế thừa từ lớp ControllerBase, nhưng nếu dùng ABP thì có thể ks thừa từ lớp AbpControllerBase, lớp này sẽ hỗ trợ một số dịch vụ phổ biến trong ABP*
  ![image](https://github.com/longdmhe161226/HttpApisABP/assets/100985816/6bb18530-20d4-4740-8997-4d9ef4ea7aba)
- *Như những API thông thường thì các ApiController này sẽ thực hiện gọi các lớp Service khác để thực hiện nghiệp vụ trong các method*
![image](https://github.com/longdmhe161226/HttpApisABP/assets/100985816/940123ce-c932-4183-b3ee-f54837446789)
- *Đấy là khi ta tự defined APIs. Mặc dù thế, ABP có thể auto defined ra các API dựa theo Service của hệ thống theo các convention*
## Hiểu hơn về Auto API Controllers
![image](https://github.com/longdmhe161226/HttpApisABP/assets/100985816/df82053c-d7eb-488f-a52a-216fad393b24)
-*Trong file HttpHostModule sẽ cấu hình như trên và options.ConventionalControllers.Create nhận một Assembly object sau đó sẽ tìm tất cả các lớp service của hệ thống và defined ra chúng*

### Khi nào chúng ta cần phải define ApiController bằng cách thủ công
  + *Khi ta sử dụng ABP thì hầu hết sẽ không tự define ApiController bằng các thủ công. Mặc dù thế nhưng cũng có thể vẫn viết ApiController trong một tiêu chuẩn cụ thể nếu muốn. Một lợi thế của việc khi mà viết Api thủ công thì ta sẽ hoàn toàn có thể sử dụng lớp HTTP để định nghĩa ra khung của APIs.*

-*Có thể sử dụng anotation [RomoteService(false)] để disable AutoApi cho Service nếu muốn*
![image](https://github.com/longdmhe161226/HttpApisABP/assets/100985816/f85ca188-15e5-42ef-ba54-c3ed8e25581e)
-*Có thể sử dụng anotation [RemoteService(IsMetadataEnabled = false)] để disable API explorer, theo em tìm hiểu và test thì nó tắt tính năng hiện lên trên swagger UI*

![image](https://github.com/longdmhe161226/HttpApisABP/assets/100985816/14521d6f-47a2-4c30-a638-3bd863cb922a)
