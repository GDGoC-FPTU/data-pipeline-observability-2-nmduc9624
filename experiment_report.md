# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600808  
**Name:** Nguyen Minh Duc  
**Date:** 2026-06-10  

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu: clean data tu `processed_data.csv` va garbage data tu `garbage_data.csv`.

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Du lieu da duoc validate, category hop le, price dung kieu so va khong co outlier bat thuong. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Agent bi anh huong boi outlier gia qua lon va cac record co chat luong kem trong tap garbage data. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent tra loi sai voi garbage data vi no dua truc tiep vao du lieu dau vao ma khong co buoc validate chat luong. Trong file garbage data co duplicate ID, sai kieu du lieu nhu price bang chu, outlier rat lon nhu Nuclear Reactor co gia 999999, va gia tri null. Logic cua agent chon san pham electronics co price cao nhat, nen outlier lam ket qua bi lech va agent xem Nuclear Reactor la lua chon tot nhat. Neu du lieu co category sai, null, duplicate hoac price khong phai so, agent co the bi loi khi doc file, bo sot record dung, hoac dua ra cau tra loi khong phu hop voi ngu canh. Thi nghiem cho thay prompt tot khong du neu knowledge base dang bi nhiem du lieu rac.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Chat luong du lieu quan trong hon prompt trong bai lab nay, vi agent chi co the tra loi dua tren data ma no doc duoc. Khi clean data da duoc validate, agent tra loi hop ly. Khi garbage data chua duoc lam sach, agent chon outlier va tao ra ket qua sai.
