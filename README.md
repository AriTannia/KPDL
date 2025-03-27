# Bike Sharing Dataset

> **Tác giả:** Hadi Fanaee-T  
> **Đơn vị:** Laboratory of Artificial Intelligence and Decision Support (LIAAD), University of Porto, INESC Porto  
> **Địa chỉ:** Campus da FEUP, Rua Dr. Roberto Frias, 378, 4200 - 465 Porto, Portugal  
> **URL:** https://archive.ics.uci.edu/dataset/275/bike+sharing+dataset

---

## 1. Tổng Quan

Bike Sharing Dataset ghi lại dữ liệu hoạt động của hệ thống chia sẻ xe đạp – một phiên bản hiện đại của việc thuê xe đạp tự động. Thay vì đến cửa hàng thuê xe, người dùng chỉ cần dùng app hoặc thẻ để mượn xe tại một trạm và trả lại xe ở trạm khác.

- **Ứng dụng:**  
  Hệ thống này được triển khai tại hơn 500 thành phố trên thế giới với hàng trăm nghìn chiếc xe, góp phần giảm ùn tắc giao thông, bảo vệ môi trường và khuyến khích lối sống lành mạnh.

---

## 2. Nền Tảng & Ý Tưởng

- **Dữ liệu được ghi nhận:**  
  Mỗi khi xe đạp được thuê, hệ thống sẽ tự động lưu lại thông tin chi tiết như:
  - **Thời gian:** Ngày, giờ, tháng, mùa, ngày trong tuần, và có phải là ngày lễ hay không.
  - **Thời tiết:** Nhiệt độ (và cảm nhận nhiệt độ), độ ẩm, tốc độ gió và tình trạng thời tiết (ví dụ: quang, mây mù, mưa nhẹ, mưa to).
  - **Thông tin người dùng:** Số lượt thuê của người dùng thường (casual) và người dùng đăng ký (registered), cùng với tổng số lượt thuê.

- **Lợi ích:**  
  Do hệ thống ghi nhận dữ liệu chi tiết (một “mạng cảm biến ảo”), ta có thể phát hiện và phân tích các sự kiện quan trọng trong thành phố cũng như dự đoán số lượng xe được thuê theo thời gian và điều kiện môi trường.

---

## 3. Các File Dữ Liệu

Dataset này bao gồm hai file chính:

- **hour.csv:**  
  - **Mô tả:** Dữ liệu được tổng hợp theo từng giờ.  
  - **Số lượng bản ghi:** ~17,379 bản ghi (mỗi bản ghi là số liệu của một giờ).
  - **Ưu điểm:** Cho thấy sự thay đổi theo từng giờ trong ngày (các giờ cao điểm, giờ nghỉ, …).

- **day.csv:**  
  - **Mô tả:** Dữ liệu được tổng hợp theo từng ngày.
  - **Số lượng bản ghi:** ~731 bản ghi (mỗi bản ghi là số liệu tổng hợp của một ngày).
  - **Ưu điểm:** Thích hợp để phân tích xu hướng hàng ngày với ít “nhiễu” hơn.

---

## 4. Các Yếu Tố Ảnh Hưởng

Số lượt xe đạp được thuê phụ thuộc vào nhiều yếu tố môi trường và thời gian, như:

- **Thời tiết:** Nhiệt độ, độ ẩm, tốc độ gió và tình trạng thời tiết (ví dụ: trời quang, mây mù, mưa).
- **Thời gian:** Giờ trong ngày, ngày trong tuần, mùa trong năm và có phải là ngày lễ hay không.

Nhờ đó, dataset này cho phép:
- **Dự Báo (Regression):** Dự đoán số xe được thuê theo thời gian và điều kiện thời tiết.
- **Phát Hiện Sự Kiện & Bất Thường:** Nhận diện các ngày có số lượt thuê bất thường (ví dụ: do bão, sự kiện lớn,…).

---

## 5. Các Trường Dữ Liệu Chính

Dataset bao gồm các trường dữ liệu sau (ngoại trừ trường `hr` không có trong day.csv):

- **instant:** Số thứ tự của bản ghi.
- **dteday:** Ngày ghi nhận.
- **season:** Mùa (1: mùa xuân, 2: mùa hè, 3: mùa thu, 4: mùa đông).
- **yr:** Năm (0: 2011, 1: 2012).
- **mnth:** Tháng (1 đến 12).
- **hr:** Giờ (0 đến 23) – chỉ có trong hour.csv.
- **holiday:** Cho biết ngày đó có phải là ngày lễ hay không.
- **weekday:** Ngày trong tuần.
- **workingday:** 1 nếu là ngày làm việc (không phải cuối tuần/ngày lễ), 0 nếu không.
- **weathersit:** Tình trạng thời tiết (1: quang, 2: mây mù, 3: mưa nhẹ, 4: mưa to).
- **temp:** Nhiệt độ (đã được chuẩn hóa, chia theo mức tối đa).
- **atemp:** "Nhiệt độ cảm nhận" (chuẩn hóa tương tự).
- **hum:** Độ ẩm (theo phần trăm).
- **windspeed:** Tốc độ gió (đã chuẩn hóa).
- **casual:** Số lượt thuê của người dùng không đăng ký.
- **registered:** Số lượt thuê của người dùng đăng ký.
- **cnt:** Tổng số lượt thuê (casual + registered).

---

## 6. Quyền Sử Dụng & Trích Dẫn

Nếu bạn sử dụng dataset này trong bài báo hay nghiên cứu, vui lòng trích dẫn theo:

```bibtex
@article{fanaee2013event,
  title={Event labeling combining ensemble detectors and background knowledge},
  author={Fanaee-T, Hadi and Gama, Joao},
  journal={Progress in Artificial Intelligence},
  pages={1--15},
  year={2013},
  publisher={Springer Berlin Heidelberg},
  doi={10.1007/s13748-013-0040-3}
}
