
# Bài tập: Ngắt ngoài + LED nhấp nháy STM32F103

## Yêu cầu đề bài
- Cấu hình **ngắt ngoài (EXTI)** cho 1 nút nhấn.  
  Khi nhấn nút, trạng thái của LED sẽ **đảo ngược**.  
- Trong quá trình đó, 1 LED khác vẫn **nhấp nháy với chu kỳ 1Hz**.  

---

## Phần cứng
- Vi điều khiển: **STM32F103C8T6 (BluePill)**  
- 2 LED + điện trở hạn dòng (220Ω)  
  - LED1: nối **PA0**  
  - LED2: nối **PA1**  
- 1 nút nhấn (button): nối **PA2** (kéo lên nội bộ)  
- Dây cắm, KIT nạp ST-LINK V2  

---

## Nguyên lý hoạt động
- **LED1 (PA0):** luôn nhấp nháy với chu kỳ 1Hz (500ms sáng, 500ms tắt).  
- **LED2 (PA1):**  
  - Bình thường: sáng/tắt đồng bộ với LED1.  
  - Khi người dùng nhấn nút (PA2), LED2 sẽ chuyển sang **đảo trạng thái** so với LED1 trong một khoảng thời gian nhất định.  
  - Sau khi hết thời gian này, LED2 sẽ trở lại trạng thái đồng bộ với LED1.  
- Ngắt ngoài (EXTI) được cấu hình để phát hiện **cạnh xuống (Falling Edge)** từ nút nhấn.  

---

## Kết quả mong đợi
- Quan sát LED1: luôn nhấp nháy đều đặn 1Hz.  
- Quan sát LED2: bình thường sáng/tắt giống LED1, nhưng sẽ **ngược trạng thái** ngay khi có thao tác nhấn nút.  

