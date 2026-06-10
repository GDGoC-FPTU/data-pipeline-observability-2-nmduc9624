[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112749&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** nmdd06092004@gmail.com  
**Name:** Nguyen Minh Duc  

---

## Mo ta

Bai lab nay xay dung mot ETL pipeline don gian cho du lieu san pham. Pipeline doc du lieu tu `raw_data.json`, kiem tra chat luong du lieu, loai bo record co `price <= 0` hoac `category` rong, sau do chuan hoa du lieu va xuat ket qua ra `processed_data.csv`.

Phan transform them cot `discounted_price` voi muc giam 10%, chuan hoa `category` ve Title Case, va them cot `processed_at` de theo doi thoi diem xu ly. Script cung in log so record da doc, hop le, loi va da luu de ho tro observability.

---

## Cach chay (How to Run)

### Prerequisites

```bash
pip install pandas pytest
```

### Chay ETL Pipeline

```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)

```bash
python generate_garbage.py
python agent_simulation.py
```

### Chay test local

```bash
pytest
```

---

## Cau truc thu muc

```text
solution.py             # ETL Pipeline script
raw_data.json           # Du lieu nguon
processed_data.csv      # Output cua pipeline
generate_garbage.py     # Tao garbage_data.csv cho stress test
agent_simulation.py     # Mo phong agent doc du lieu
experiment_report.md    # Bao cao thi nghiem
README.md               # File huong dan
```

---

## Ket qua

Voi du lieu mau trong `raw_data.json`, pipeline doc 5 records. Trong do co 3 records hop le duoc giu lai va 2 records bi loai do du lieu khong hop le: mot record co gia am va mot record co category rong. File output `processed_data.csv` gom cac cot goc cong them `discounted_price` va `processed_at`.
