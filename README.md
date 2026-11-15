# MiniCAD 2D

Web app vẽ CAD 2D cơ bản, chạy hoàn toàn trên trình duyệt (một file `index.html`, không cần build, không cần server).

## Tính năng
- Vẽ: đường thẳng, polyline (đóng/mở), chữ nhật, đường tròn, cung 3 điểm
- Sửa: chọn (click / kéo khung window-crossing), di chuyển, sao chép, xoay, xóa
- Bắt điểm: lưới, điểm cuối, trung điểm, tâm, góc phần tư, Ortho (F8 hoặc giữ Shift)
- Dòng lệnh: gõ số (độ dài), `x,y`, `@dx,dy`, `@dài<góc`, tên lệnh (`line`, `rect`, `circle`, `ze`…)
- Layer (màu, ẩn/hiện), thuộc tính (độ dài, diện tích, bán kính…), công cụ đo
- Hoàn tác / làm lại, tự lưu trong trình duyệt (localStorage)
- Lưu/mở JSON; xuất SVG, DXF, PNG

## Đưa lên GitHub Pages (miễn phí)
1. Đăng nhập GitHub → **New repository** → đặt tên (ví dụ `minicad`) → để **Public** → Create.
2. Bấm **Add file → Upload files**, kéo `index.html` và `README.md` vào → **Commit changes**.
3. Vào **Settings → Pages**. Ở mục *Build and deployment*, chọn **Source: Deploy from a branch**, **Branch: main**, thư mục **/ (root)** → **Save**.
4. Đợi khoảng 1 phút. Web app sẽ chạy tại `https://<tên-github>.github.io/minicad/`.

Hoặc dùng dòng lệnh:

```bash
git init -b main
git add index.html README.md
git commit -m "MiniCAD 2D"
git remote add origin https://github.com/<tên-github>/minicad.git
git push -u origin main
```
