
### ⚠️ QUY TẮC VÀNG (Đọc kỹ kẻo mất công)

Nhìn vào hình 3, bạn thấy thư mục **`TemplatePlot`** trong `ReplicatedStorage` chứ?

* **Mọi chỉnh sửa phải làm trong `TemplatePlot**`.
* **KHÔNG** sửa trực tiếp ở ngoài `Workspace > Plots`. Vì khi game bắt đầu, hệ thống sẽ copy cái `TemplatePlot` ra cho người chơi mới. Nếu bạn sửa ở Workspace, người chơi mới vào sẽ không thấy thay đổi đó.

---

### GIAI ĐOẠN 1: THAY ĐỔI CƠ CHẾ SẢN XUẤT (Biến Máy thành Tổ Đá)

Trong Tycoon, "Dropper" (Máy thả) là thứ tạo ra tiền. Chúng ta sẽ biến nó thành "Tổ Đá".

**Bước 1: Tìm vị trí**

* Vào `ReplicatedStorage > TemplatePlot > Products` (hoặc có thể là `Buttons` nếu kit này gộp chung).
* Thường `Products` chứa model của cái máy, còn `Buttons` chứa cái nút để mua máy đó.

**Bước 2: Thay đổi hình dạng (Reskin)**

* Mở thư mục `Products`. Bạn sẽ thấy các model tên kiểu `Dropper1`, `Mine1`.
* Lôi nó ra Workspace để dễ sửa.
* Xóa cái hình hộp máy móc đi. Thay bằng model **Hang Đá** hoặc **Quả Trứng** bạn vẽ bên Blockbench.
* **Quan trọng:** Giữ nguyên cái phần "miệng nhả" (thường là một Part trong suốt tên là `DropPoint` hoặc tương tự) để đá vẫn rơi ra đúng chỗ.
* Sau khi sửa xong, kéo nó trả lại vào thư mục `Products` cũ trong `TemplatePlot`.

---

### GIAI ĐOẠN 2: THAY ĐỔI CƠ CHẾ TIẾN HÓA (Biến Máy Nâng Cấp thành Cổng Nguyên Tố)

Trong hình 2 và 3 đều có thư mục **`Upgrades`**. Đây là nơi chứa các máy làm tăng giá trị tiền.

**Bước 1: Quy hoạch hệ**

* *Upgrade 1*  Đổi tên thành **"Fire Gate"** (Cổng Lửa).
* *Upgrade 2*  Đổi tên thành **"Water Gate"** (Cổng Nước).

**Bước 2: Sửa model**

* Vào `ReplicatedStorage > TemplatePlot > Upgrades`.
* Lấy model ra sửa. Biến nó thành cái Cổng Torii hoặc Vòng Tròn Ma Thuật.
* **Mẹo hiệu ứng:** Với Cổng Lửa, hãy thêm một `PointLight` màu đỏ và `Fire Particle` vào. Khi đá chạy qua nhìn sẽ như đang được nung chín.

**Bước 3: Tạo nút mua (Buttons)**

* Vào `ReplicatedStorage > TemplatePlot > Buttons`.
* Bạn cần đổi tên các nút hiển thị trên đầu (BillboardGui) để người chơi biết họ đang mua gì. Ví dụ: Đổi text từ "Buy Upgrader 1" thành "Build Fire Gate".

---

### GIAI ĐOẠN 3: CÂN BẰNG GAME (Chỉnh sửa thông số)

Nhìn vào hình 3, thư mục **`Game Settings > Balancing`** là nơi bạn chỉnh độ khó/dễ.

**1. Chỉnh giá Rebirth (Chuyển sinh):**

* Theo hướng dẫn trong script `Read Me`, bạn vào `ReplicatedStorage > Game Settings > Balancing > RebirthPrice`.
* Đổi số `Cost` (Giá) sao cho hợp lý. Đừng để cao quá người chơi nản, cũng đừng thấp quá họ phá đảo nhanh.

**2. Reset dữ liệu khi test:**

* Khi bạn test game, tiền sẽ lưu lại. Muốn test từ đầu như người chơi mới?
* Theo hướng dẫn: Vào `ReplicatedStorage > Game Settings > DataSave`.
* Đổi con số ở đó (ví dụ từ `PlayerData1` thành `PlayerData2`). Game sẽ hiểu là bản save mới.

---

### GIAI ĐOẠN 4: MỞ RỘNG (Thêm đá mới)

Dựa vào hướng dẫn `---MORE UPGRADES---` trong ảnh 2:

* **Nguyên tắc:** Muốn thêm máy mới, bạn KHÔNG CẦN CODE.
* **Cách làm:**

1. Vào `TemplatePlot > Upgrades`, chọn một cái có sẵn (ví dụ `Fire Gate`), bấm **Duplicate (Ctrl + D)**. Đổi tên thành `Ice Gate`.
2. Vào `TemplatePlot > Buttons`, chọn nút mua của cái cũ, bấm **Duplicate**.
3. Đổi tên nút mới sao cho khớp với tên cái máy mới (`Object` property trong nút phải trỏ về cái máy mới).
4. Sửa giá tiền (`Price`) và lượng tiền cộng thêm (`Multiplier`) trong thuộc tính của nút/máy.

---

### 📝 BÀI TẬP CHO BẠN HÔM NAY

Hãy tập trung vào **Giai Đoạn 1 & 2** trước.

1. Vào `TemplatePlot > Buttons`. Tìm cái nút mua máy đầu tiên (thường là `Button1` hoặc `Dropper1Button`).
2. Đổi cái Model của nút đó thành hình một **Cục Đá nhỏ**.
3. Vào `TemplatePlot > Upgrades`. Lôi cái `Upgrader1` ra, xóa model cũ, thay bằng một cái **Cổng màu đỏ**.
4. Bấm **Play** để xem sự thay đổi.

Khi nào làm xong bước thay hình ảnh này, game của bạn sẽ lột xác ngay lập tức! Bạn có gặp khó khăn khi tìm thư mục `TemplatePlot` không?
