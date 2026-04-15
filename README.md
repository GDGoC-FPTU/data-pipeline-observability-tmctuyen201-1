[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23573944&assignment_repo_type=AssignmentRepo)

# Day 10 Lab: Data Pipeline & Data Observability

**Student ID:** 2A202600324
**Name:** TuyenTMC

---

## Mo ta

Day 10 Lab: Build Your First Automated ETL Pipeline. Hoan thanh cac chuc nang Extract, Validate, Transform, Load. Xu ly du lieu tu raw_data.json, loai bo cac record khong hop le (price <= 0 hoac category rong), tinh gia giam 10% va them timestamp.

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
# Generate garbage data first
python generate_garbage.py

# Test with clean data
python agent_simulation.py

# Test with garbage data
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
├── raw_data.json            # Input data
├── generate_garbage.py      # Generates test data
├── agent_simulation.py     # Agent simulation
└── README.md                # File nay
```

---

## Ket qua

- Total records in raw_data.json: 5
- Valid records after validation: 3
- Dropped records: 2 (1 negative price, 1 empty category)
- Discounted price calculated: price \* 0.9
- Category normalized to Title Case
- Timestamp added: processed_at column
