# Configurable Multimode Traffic Light Control System

## 📝 Giới thiệu
Dự án này triển khai hệ thống điều khiển đèn giao thông tại ngã tư sử dụng vi điều khiển **STM32F103C6**. Hệ thống hỗ trợ 4 chế độ hoạt động (Modes), cho phép người dùng theo dõi thời gian thực qua LED 7 đoạn và tùy chỉnh thời gian các đèn thông qua các nút nhấn tương tác.

## 🚀 Tính năng chính
* **Hệ thống 4 Chế độ (Modes):**
    * **Mode 1:** Chế độ tự động bình thường (Đỏ 5s, Vàng 2s, Xanh 3s).
    * **Mode 2:** Điều chỉnh thời gian đèn Đỏ (Red).
    * **Mode 3:** Điều chỉnh thời gian đèn Vàng (Amber).
    * **Mode 4:** Điều chỉnh thời gian đèn Xanh (Green).
* **Giao tiếp người dùng:**
    * **3 nút nhấn:** Lần lượt để chọn chế độ, tăng giá trị thời gian và lưu cài đặt.
    * **4 LED 7 đoạn:** Hiển thị đồng thời giá trị thời gian và số thứ tự Mode.
* **Logic thông minh:** Đảm bảo quy luật giao thông $Red = Green + Amber$ thông qua hàm tự động điều chỉnh logic thời gian.

## 🛠 Kỹ thuật và Công cụ
* **Phần cứng:** STM32F103C6, LED 7-Segment, Traffic Light LEDs.
* **Lập trình:** Ngôn ngữ C (Embedded), STM32CubeIDE.
* **Mô phỏng:** Proteus.

### Sơ đồ hệ thống & Mô phỏng
<p align="center">
  <img src="https://raw.githubusercontent.com/anhthu057/Configurable_Multimode_Traffic_Light_Control_System/images/state_machine.png" width="450" title="Sơ đồ FSM">
  <br>
  <em>Sơ đồ máy trạng thái (FSM) quản lý các Mode</em>
  <br><br>
  <img src="https://raw.githubusercontent.com/anhthu057/Configurable_Multimode_Traffic_Light_Control_System/images/PROTEUS.png" width="600" title="Sơ đồ Proteus">
  <br>
  <em>Giao diện mô phỏng trên Proteus</em>
</p>

## 📂 Kiến trúc phần mềm
Dự án được tổ chức theo module để dễ dàng bảo trì và mở rộng:
* **FSM (Finite State Machine):** Quản lý luồng vận hành chính và các chế độ tùy chỉnh.
* **Software Timer:** Xử lý đa nhiệm không dùng hàm `delay()`, cho phép hệ thống phản hồi nút nhấn tức thì.
* **Button Debouncing:** Thuật toán chống rung phím, hỗ trợ nhấn đơn và nhấn giữ để tăng giá trị nhanh.

## 🎥 Minh họa hoạt động
* **Video Demo:** [Xem tại đây](https://drive.google.com/file/d/1Iix2whbuMed6j3miu3Ah4dJGnDOB9TL5/)
