# MiniCAD

Web app CAD 2D kèm 3D cơ bản, chạy hoàn toàn trên trình duyệt, chỉ một file `index.html` (không cần cài đặt, không cần server). Giao diện kiểu AutoCAD: nền tối, ribbon Draw/Modify/Annotate, dòng lệnh có gợi ý.

Demo: https://thinhnvhusthithub.github.io/minicad/

## Chạy
- Mở `index.html` bằng trình duyệt, hoặc dùng GitHub Pages (Settings → Pages → Branch `main` / root).
- Bản vẽ 2D tự lưu trong trình duyệt (localStorage). Dùng **Save JSON** để lưu ra file.
- Chuyển chế độ bằng nút **2D / 3D** ở thanh trên.

## Dòng lệnh
Gõ lệnh ngay trên vùng vẽ (không cần bấm vào ô lệnh). Space hoặc Enter kết thúc/xác nhận lệnh; Enter trống lặp lại lệnh trước; Esc hủy; chuột phải kết thúc.
Nhập tọa độ: `x,y`, tương đối `@dx,dy`, cực `@dài<góc`.
Với lệnh sửa (Move, Copy…): chọn đối tượng trước hoặc sau khi gõ lệnh, Enter để kết thúc việc chọn.

### Phím tắt lệnh 2D
| Phím tắt | Lệnh | Phím tắt | Lệnh |
|---|---|---|---|
| L | Line | M | Move |
| PL / PLINE | Polyline | CO / CP | Copy |
| REC | Rectangle | RO | Rotate |
| POL | Polygon | SC | Scale |
| C | Circle | MI | Mirror |
| C2P / C3P | Circle 2P / 3P | S | Stretch |
| A | Arc 3 điểm | TR | Trim |
| ASC | Arc Start-Center-End | EX | Extend |
| EL / ELC | Ellipse (trục) / (tâm) | BR | Break |
| SPL | Spline | J | Join |
| PO | Point | F | Fillet |
| XL / RAY | Xline / Ray | CHA | Chamfer |
| REG | Region | O | Offset |
| BO | Boundary | AR | Array chữ nhật |
| H | Hatch | ARRAYP | Array tròn |
| T | Text | X | Explode |
| DLI | Dimension | E / DEL | Erase |
| DI | Distance | MA | Match Properties |
| DIV | Divide | QSEL | Quick Select |
| ME | Measure | V / P | Select / Pan |

### Lệnh hệ thống (gõ vào dòng lệnh)
`undo` (`u`), `redo`, `zoom` (`ze`), `regen`, `all` (chọn tất cả), `grid`, `snap`, `ortho`, `osnap`, `lwt` (hiện lineweight), `pickbox N` (cỡ ô chọn), `cursor N` (cỡ con trỏ), `layer TÊN` (đổi/tạo layer hiện hành), `cl` (đóng hình khi vẽ polyline/spline), `3d`, `2d`.

### Phím nóng
| Phím | Tác dụng |
|---|---|
| F3 | Bật/tắt snap lưới |
| F4 | Bật/tắt object snap |
| F7 | Bật/tắt lưới |
| F8 | Bật/tắt ortho |
| Ctrl+Z / Ctrl+Y (Ctrl+Shift+Z) | Undo / Redo |
| Ctrl+A | Chọn tất cả |
| Ctrl+S | Lưu JSON |
| Delete / Backspace | Xóa đối tượng đang chọn |
| Esc | Hủy lệnh |

## 2D
- **Vẽ:** Line, Polyline, Rectangle, Polygon (nội tiếp/ngoại tiếp, số cạnh), Circle (tâm-bán kính, 2P, 3P), Arc (3P, S-C-E), Ellipse, Spline, Point, Xline, Ray, Hatch, Text, Dimension, Distance.
- **Sửa:** Move, Copy, Rotate, Scale (hệ số hoặc tham chiếu), Mirror, Stretch (cửa sổ crossing), Trim, Extend, Break, Join, Fillet, Chamfer, Offset, Array (chữ nhật/tròn), Explode, Erase.
- **Region/Boundary:** tạo vùng kín từ nét vẽ rời, hỗ trợ lỗ bên trong; Hatch cũng nhận vùng kín từ nét rời.
- **Divide / Measure:** chia đối tượng thành N đoạn hoặc theo độ dài, đặt Point.
- **Thuộc tính:** Linetype (continuous, dashed, hidden, center, phantom, dot, dashdot), Lineweight (nút LWT bật hiển thị), màu; Layer có màu, ẩn, Freeze, Lock, linetype/lineweight riêng; Match Properties; Quick Select; bảng Properties sửa số liệu trực tiếp.
- **Object snap:** Endpoint, Midpoint, Center, Quadrant, Intersection, Node, Insert; snap lưới; ortho.
- **Chọn:** ô chọn (pickbox) vuông; kéo trái→phải = window (chọn vật nằm trọn), phải→trái = crossing (chọn vật chạm). Shift để thêm/bớt.
- **Xem:** lăn chuột zoom, kéo giữa/Pan để di chuyển, **Zoom extents**.

## 3D
Box, Cylinder, Cone, Sphere, Extrude (từ vùng 2D, giữ lỗ), Revolve (quanh trục, góc trong Options), Union, Subtract, Intersect, Press/Pull (kéo/đẩy mặt phẳng), Move, Copy, Delete; chỉnh kích thước/vị trí trong Properties.
- Chọn: click, Shift để thêm/bớt; phím mũi tên dịch XY, PgUp/PgDn dịch Z.
- Camera: Orbit (kéo; chuột phải cũng xoay, chuột giữa pan, lăn để zoom); nút Top/Front/Right/Iso (phím 1–4), Perspective, Wireframe.
- Lệnh gõ: `box`, `cyl`, `cone`, `sph`, `ext`, `rev`, `union`, `su` (subtract), `in` (intersect), `pp`, `m`, `co`, `e`.

## Nhập/Xuất
- **Nhập:** DXF (layer, linetype, lineweight, màu, ellipse, spline, point, xline, ray…), JSON.
- **Xuất 2D:** DXF, SVG, PNG, JSON.
- **Xuất 3D:** OBJ, STL.

## Cập nhật bản mới
Tải `index.html` mới lên repo (Add file → Upload files), ghi đè file cùng tên, rồi Commit. GitHub Pages cập nhật sau khoảng 1 phút.
