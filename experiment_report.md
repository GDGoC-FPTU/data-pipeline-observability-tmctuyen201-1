# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600324
**Name:** TuyenTMC
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario                          | Agent Response                                                          | Accuracy (1-10) | Notes                                                                                                             |
| --------------------------------- | ----------------------------------------------------------------------- | --------------- | ----------------------------------------------------------------------------------------------------------------- |
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200.            | 9               | Agent correctly identified the most expensive electronics product. Clean data yielded accurate, reliable results. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2               | Agent selected an extreme outlier with suspicious pricing. Garbage data caused catastrophic failure.              |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi su dung du lieu rac (garbage data), Agent tra loi sai nghiem trong vi co nhieu van de ve chat luong du lieu:

1. **Duplicate IDs**: Garbage data co id = 1 lap lai 2 lan (Laptop va Banana), tao su nham lan trong he thong. Agent khong the phan biet giua cac record hop le va trung lap.

2. **Wrong Data Types**: Mot so record co gia tri "ten dollars" thay vi so, khiến Agent khong the so sanh gia tri. Price bi loi type se tao ra ket qua tinh toan sai.

3. **Extreme Outliers**: Nuclear Reactor co gia 999999, la mot outlier cuc doc. Agent chon san pham nay vi no co gia cao nhat, nhung day la du lieu khong thuc te.

4. **Null Values**: Co record voi id = None, product = "Ghost Item", price = 0, category = None. Du lieu null khong co y nghia, gay ra loi khi xu ly.

5. **Zero Price**: Gia = 0 (Phantom Item) la gia tri khong hop le nhung van con trong data. Agent khong biet rang gia 0 la bat thuong.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Du lieu chat luong cao la nen tang cho moi thuat toan AI hoat dong chinh xac. Neu du lieu dau vao bi loi, nhieu cau prompt tot cung khong the cuu chua. Chat luong du lieu la yeu to quyet dinh - "garbage in, garbage out". Vi vay, viec Validate va lam sach du lieu (Data Observability) la buoc khong the thieu trong bat ky he thong ETL nao.
