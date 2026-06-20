# Đồ án 3: Xích Markov

Đồ án môn **Toán ứng dụng và thống kê (MTH00051)**, năm học 2025–2026. Dự án khảo sát hai bài toán về xích Markov hữu hạn, kết hợp phân tích lý thuyết, tính toán số và mô phỏng Monte Carlo bằng Python.

> [!IMPORTANT]
> Dự án sử dụng quy ước ma trận chuyển theo cột: $P_{ij}=\Pr(X_{n+1}=i\mid X_n=j)$. Vì vậy, tổng mỗi cột của $P$ bằng 1 và phân phối được cập nhật theo $\pi_n=P\pi_{n-1}$.

## Nội dung

### Bài toán 1 — Tổng xúc xắc modulo 7

Notebook [`cau1.ipynb`](./cau1.ipynb) mô hình hóa

$$
X_n=S_n\bmod 7,
$$

trong đó $S_n$ là tổng kết quả sau $n$ lần tung một xúc xắc cân bằng. Nội dung chính gồm:

- xây dựng không gian trạng thái, ma trận chuyển và phân phối đầu;
- tính phân phối của $S_n\bmod 7$ qua từng thời điểm;
- tìm phân phối dừng bằng phương pháp khử Gauss;
- kiểm tra tính chính quy và tốc độ hội tụ;
- tính xác suất quá trình dừng không quá $n$ lần tung khi tổng lần đầu chia hết cho 7.

Xích có phân phối dừng đều $(1/7,\ldots,1/7)^T$ và $P^2$ dương hoàn toàn. Khi xuất phát tại trạng thái 0, phân phối không đạt chính xác phân phối dừng ở một thời điểm hữu hạn; với ngưỡng sai số $10^{-12}$, thời điểm hội tụ đầu tiên được ghi nhận là $t=16$.

### Bài toán 2 — Ba xích Markov độc lập

Notebook [`cau2.ipynb`](./cau2.ipynb) nghiên cứu chuyển động độc lập của Drogon, Rhaegal và Viserion trên cùng một không gian gồm $M$ trạng thái. Các kết quả chính:

- kỳ vọng số lần Drogon ở nhà từ thời điểm 0 đến 24 là $25s_0$;
- trạng thái chung $(X_n,Y_n,Z_n)$ tạo thành một xích Markov gồm $M^3$ trạng thái;
- ma trận chuyển chung là $P\otimes P\otimes P$;
- kỳ vọng thời gian để cả ba cùng trở về nhà là $1/s_0^3$;
- mô phỏng Monte Carlo được dùng để đối chiếu với các công thức lý thuyết.

Với ma trận minh họa đối xứng có $M=3$ và $s_0=1/3$, các giá trị lý thuyết lần lượt là $25/3\approx8{,}3333$ và $27$. Notebook thực hiện 20.000 lần mô phỏng để kiểm chứng hai kết quả này.

## Công nghệ sử dụng

- Python 3.13
- Jupyter Notebook
- NumPy
- pandas
- Matplotlib

## Cấu trúc dự án

```text
.
├── cau1.ipynb   # Bài toán tổng xúc xắc modulo 7
├── cau2.ipynb   # Bài toán ba xích Markov độc lập
├── DoAn3.pdf    # Đề bài
├── Report.pdf   # Báo cáo đồ án
└── README.md
```

## Chạy notebook

Tạo môi trường ảo và cài các thư viện cần thiết:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install numpy pandas matplotlib jupyter
```

Khởi động Jupyter:

```powershell
jupyter lab
```

Mở `cau1.ipynb` hoặc `cau2.ipynb`, sau đó chạy toàn bộ các cell theo thứ tự từ trên xuống.

> [!NOTE]
> Hai notebook đã được thực thi bằng Python 3.13.7 và không chứa lỗi thực thi trong kết quả được lưu kèm.

## Tài liệu

- [Đề bài đồ án](./DoAn3.pdf)
- [Báo cáo hoàn chỉnh](./Report.pdf)

## Thành viên

- Trần Kim Hữu — lớp 24TNT1TN
- Nguyễn Danh Phương — lớp 24TNT1TN
