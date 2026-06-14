# Buổi 1 — Giới thiệu Computer Vision & Bản chất ảnh số

## Mục tiêu

Sau buổi này bạn phải trả lời được 3 câu hỏi sau mà không cần nhìn tài liệu:

- Ảnh trong máy tính thực chất là gì?
- Tại sao ảnh màu lại có shape `(H, W, 3)` còn ảnh đen trắng chỉ có `(H, W)`?
- Tại sao khi đọc ảnh bằng OpenCV rồi hiển thị bằng Matplotlib màu sắc lại bị sai?

Nếu chưa trả lời được, hãy đọc lại phần lý thuyết trước khi làm bài tập.

---

## Cấu trúc thư mục

```
buoi-1/
├── README.md               # file này
├── bai_tap_buoi_1.ipynb    # bài tập về nhà — chỗ bạn sẽ code
└── anh_mau.jpg             # ảnh mẫu để chạy thử (thay bằng ảnh của bạn cũng được)
```

---

## Cài đặt môi trường

Nếu chưa cài, chạy lần lượt các lệnh sau trong terminal:

```bash
conda create -n cv_course python=3.10 -y
conda activate cv_course
pip install numpy opencv-python matplotlib
```

Kiểm tra cài đặt thành công:

```bash
python -c "import cv2, numpy, matplotlib; print('OK')"
```

Nếu in ra `OK` là xong. Nếu báo lỗi, chụp màn hình và hỏi trong nhóm lớp.

---

## Kiến thức cần nắm sau buổi này

**Ảnh số là gì**

Ảnh không phải là một bức tranh mà máy tính "nhìn thấy" — nó là một mảng số nguyên. Mỗi số là giá trị độ sáng của một điểm ảnh (pixel), nằm trong khoảng 0 đến 255. Ảnh càng có nhiều pixel thì càng sắc nét, nhưng cũng càng nặng.

**Kênh màu (channel)**

Ảnh màu RGB lưu 3 ma trận chồng lên nhau — một cho màu đỏ, một cho màu xanh lá, một cho màu xanh dương. Kết hợp 3 kênh lại ta có ảnh đầy đủ màu sắc. Ảnh grayscale chỉ cần 1 kênh vì nó chỉ lưu độ sáng, không lưu màu sắc.

**Thứ tự kênh màu trong OpenCV**

OpenCV đọc và lưu ảnh theo thứ tự **BGR** (Blue-Green-Red), không phải RGB như thông thường. Đây là quyết định lịch sử từ hồi thư viện mới ra đời và giờ không thể đổi lại vì sẽ phá vỡ hàng triệu dòng code hiện có. Bạn cần nhớ điều này vì nó gây ra lỗi màu sắc rất thường gặp — ảnh đỏ hiển thị thành xanh và ngược lại.

**NumPy là nền tảng**

Mọi thao tác với ảnh trong Python đều thực chất là thao tác với NumPy array. Hiểu slicing, indexing, và các phép tính trên array là kỹ năng bạn sẽ dùng xuyên suốt cả khóa học.

---

## Làm bài tập

Mở file `bai_tap_buoi_1.ipynb` trong Jupyter Notebook và làm theo thứ tự từ Bài 1 đến Bài 6.

Một số lưu ý:
- Mỗi bài chỉ có phần `# TODO:` — bạn phải tự viết code, không có code mẫu
- Đọc kỹ comment trước khi code, yêu cầu đôi khi có ràng buộc cụ thể (ví dụ: không được dùng hàm X)
- Chạy `Kernel → Restart & Run All` một lần trước khi nộp để chắc chắn notebook chạy được từ đầu đến cuối

---

## Nộp bài

Nộp file `bai_tap_buoi_1.ipynb` đã có đầy đủ output lên nhóm lớp trước **23:59 ngày hôm trước buổi học tiếp theo**.

File chưa chạy hoặc thiếu output sẽ không được chấm.
