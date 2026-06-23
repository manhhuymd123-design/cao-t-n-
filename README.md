# cao-tan
<img width="2560" height="2560" alt="image" src="https://github.com/user-attachments/assets/46349c3b-5e00-4b01-8309-c52ccfece95e" />
# Nguyên Lý Hoạt Động Mạch Khuếch Đại Siêu Cao Tần (RF/Microwave Amplifier Operation)
Hệ thống siêu cao tần luôn được phân tích độc lập trên hai chế độ tách biệt: **Chế độ một chiều (DC Bias)** để nuôi Transistor và **Chế độ xoay chiều (AC/RF)** để khuếch đại tín hiệu. Tài liệu này phân tích chi tiết nguyên lý hoạt động của hai cấu hình mạch phân cực phổ biến.
## 1. Nguyên Lý Hoạt Động Mạch (a) - Nguồn Đôi
Cấu hình này sử dụng một nguồn dương, một nguồn âm độc lập và thực hiện nối đất trực tiếp cực Source.
### 🔹 Chế độ một chiều (DC Bias)
* **Cấp nguồn:** * Nguồn âm **V_G = -2 V** được đưa vào cực Gate thông qua cuộn cảm chặn cao tần (RFC).
  * Nguồn dương **V_D = 5 V** được đưa vào cực Drain qua một cuộn cảm RFC khác.
  * Cực Source được nối đất trực tiếp: **V_S = 0 V**.
* **Thiết lập điểm làm việc tĩnh:** Hiệu điện áp giữa các cực được xác định:
  * **V_GS = V_G - V_S = -2 V - 0 V = -2 V**
  * **V_DS = V_D - V_S = 5 V - 0 V = 5 V**
* **Trạng thái:** Điện áp **V_GS = -2 V** mở kênh dẫn bên trong transistor ở một mức độ vừa phải, định hình dòng điện một chiều tĩnh **I_DQ** chạy ổn định từ nguồn V_D, qua cực Drain, xuyên qua kênh dẫn xuống cực Source rồi về đất.
* Các tụ điện ở ngõ vào và ngõ ra đóng vai trò như một mạch hở đối với dòng DC, ngăn không cho điện áp một chiều rò rỉ ra các tầng linh kiện phía trước hoặc phía sau.
### 🔹 Chế độ xoay chiều (AC/RF)
* **Đường đi của tín hiệu:** Tín hiệu siêu cao tần (RF) từ ngõ vào đi xuyên qua tụ nối tầng (tụ có trở kháng rất nhỏ ở tần số cao nên dòng RF qua dễ dàng) để đặt thẳng vào cực Gate.
* **Khuếch đại:** Sự biến thiên điện áp của tín hiệu RF tại cực Gate điều khiển độ mở của kênh dẫn, từ đó kiểm soát dòng dòng điện chạy qua transistor. Quá trình này tạo ra một tín hiệu RF biến thiên tương tự nhưng có năng lượng lớn hơn rất nhiều tại cực Drain (tín hiệu đã được khuếch đại). Tín hiệu khuếch đại tiếp tục đi qua tụ ngõ ra để truyền đến tải.
* **Tính năng cách ly (Tách biệt AC - DC):**
  * Các cuộn cảm RFC ở cực Gate và Drain có trở kháng rất lớn (**Z_L = j*omega*L**) ở tần số siêu cao tần, đóng vai trò như một mạch hở, chặn đứng tín hiệu RF không cho rò ngược về các nguồn cấp DC (V_G, V_D).
  * Các tụ lọc nguồn (Bypass) nối đất ở đầu nguồn DC có trở kháng bằng 0 đối với RF, dập tắt hoàn toàn bất kỳ sóng RF nhiễu nào còn sót lại để bảo vệ độ sạch của nguồn nuôi.
 --
## 2. Nguyên Lý Hoạt Động Mạch (b) - Nguồn Đơn (Nâng Áp Source)
Cấu hình này sử dụng phương pháp nâng điện áp cực Source lên cao hơn đất để thiết lập điện áp ngược cho chân Gate mà không cần dùng đến nguồn âm.
### 🔹 Chế độ một chiều (DC Bias)
* **Cấp nguồn:** * Cực Gate được nối đất thông qua một cuộn cảm. Vì cuộn cảm đối với dòng một chiều chỉ là một sợi dây dẫn thuần túy (điện trở bằng 0), nên điện áp tại cực Gate bị ghim chặt ở mức **V_G = 0 V**.
  * Cực Source được cấp một nguồn dương **V_S = 2 V** qua cuộn cảm.
  * Cực Drain được cấp nguồn dương lớn hơn: **V_D = 7 V** qua cuộn cảm.
* **Thiết lập điểm làm việc tĩnh:** Hiệu điện áp thực tế đặt lên transistor:
  * **V_GS = V_G - V_S = 0 V - 2 V = -2 V**
  * **V_DS = V_D - V_S = 7 V - 2 V = 5 V**
* **Trạng thái:** Nhờ cách nâng điện áp cực Source lên 2 V, transistor vẫn nhận được một điện áp điều khiển **V_GS = -2 V** giống hệt như mạch (a), tạo ra cùng một dòng điện định thiên **I_DQ** chạy từ Drain sang Source mà không cần đến một bộ tạo nguồn âm độc lập.
### 🔹 Chế độ xoay chiều (AC/RF)
* **Quá trình khuếch đại:** Tín hiệu RF đi vào cực Gate và đi ra từ cực Drain tương tự như mạch (a). Cuộn cảm nối đất ở cực Gate và các cuộn cảm nối nguồn ở cực Drain, cực Source tiếp tục nhiệm vụ chặn tín hiệu RF lọt vào đường nguồn DC.
* **Tạo đất ảo tại cực Source:** Đối với mạch khuếch đại cấu hình Source chung (Common Source), cực Source bắt buộc phải được nối đất về mặt xoay chiều để tín hiệu đạt độ lợi lớn nhất. Tuy nhiên, cực Source lúc này đang dính điện áp DC 2 V.
* **Giải pháp:** Một tụ điện thoát (Bypass Capacitor) được mắc song song từ cực Source xuống đất. Ở tần số siêu cao tần, tụ điện này có trở kháng cực kỳ nhỏ (**Z_C = 1 / (j*omega*C) ~ 0**). Nó hoạt động như một dây dẫn ngắn mạch đối với tín hiệu RF, biến cực Source thành một điểm **"Đất ảo" (AC Ground)** về mặt xoay chiều, trong khi vẫn giữ nguyên điện áp tĩnh 2 V về mặt một chiều.
-- 
## 3. Tóm Tắt Chức Năng Thành Phần Linh Kiện

| Linh Kiện | Vai Trò Đối Với DC | Vai Trò Đối Với AC / RF |
| :--- | :--- | :--- |
| **Tụ nối tầng (Series C)** | Hở mạch (Ngăn áp DC lọt ra ngoài) | Ngắn mạch (Cho tín hiệu RF đi qua) |
| **Cuộn cảm chặn (RFC)** | Dẫn điện (Cấp nguồn nuôi cho cực) | Hở mạch (Chặn RF rò vào nguồn DC) |
| **Tụ thoát nguồn (Bypass C)** | Hở mạch (Giữ nguyên điện áp phân cực) | Ngắn mạch (Tạo điểm đất ảo AC Ground) |


