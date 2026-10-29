# Complete Data Visualization & Exploratory Data Analysis (EDA) with Python, Matplotlib and Seaborn — Beginner to Real-World Projects

> **Language:** Easy Roman Urdu (English technical terms original rakhe gaye hain)
> **Level:** Bilkul Beginner (Zero se start)
> **File:** `Complete_Seaborn_EDA_Course_Roman_Urdu.md`
> **Tested versions:** Python 3.10+, pandas 2.x/3.x, NumPy 1.26+/2.x, Matplotlib 3.8+, Seaborn 0.13+

---

## Course Ko Kaise Use Karein? (Students Ke Liye)

1. Course ko **upar se neeche** order mein parhein. Har chapter pichle chapter par bana hai.
2. Har code ko **khud type karein** (copy-paste kam karein). Typing se hi code samajh aata hai.
3. Har code ke baad **"Line-by-line explanation"** zaroor parhein.
4. Har chapter ke end par **Practice Task** aur **Quiz** khud solve karein.
5. Agar error aaye to **Section 11 (Troubleshooting)** dekhein.

> ⚠️ **Zaroori Note (Synthetic Data):** Is course mein jitne bhi datasets hain (Student Performance, Sales, Hospital, E-commerce, Weather) woh **Python code se banaye gaye practice (synthetic) data** hain. Yeh kisi **asal school, hospital ya company ka real record nahi** hain. Inka maqsad sirf seekhna hai. Asal projects mein aap apna real CSV/Excel data load karenge.

---

## Fehrist (Table of Contents)

| Part | Topic |
|---|---|
| 1 | Course Setup — Basic Concepts, Installation |
| 2 | Common Dataset (Student Performance) + Data Inspection |
| 3 | Complete Graphs Course — Chapter 1 se 11 |
| 4 | Parameters Ki Complete Guide |
| 5 | Graph Customization |
| 6 | EDA Workflow |
| 7 | Complete Real-World EDA Project |
| 8 | Additional Practice Datasets |
| 9 | Common Errors and Troubleshooting |
| 10 | Final Revision, MCQs, Coding Questions, Projects, Viva |

---

# PART 1: Course Setup — Zero Se Start

## 1.1 Data Visualization Kya Hai?

**Data Visualization** ka matlab hai: **data (numbers) ko graph, chart ya picture mein badalna** taake hum usay jaldi samajh sakein.

**Real-life example:**
Aap ke paas 40 students ke marks ki list hai:

```
55, 56, 40, 30, 88, 62, 71, 48, 90, 25 ...
```

Ab aap se poocha jaye: "Class ki performance kaisi hai?" Numbers ki list dekh kar jawab dena mushkil hai. Lekin agar aap in marks ka **bar chart** bana dein, to aap ek nazar mein dekh lenge ke kaun sa student upar hai aur kaun neeche.

> **Ek line mein:** Insaan ka dimagh **numbers se zyada pictures jaldi samajhta hai.** Isi liye graph banate hain.

## 1.2 EDA Kya Hai?

**EDA = Exploratory Data Analysis.**

- **Exploratory** = Talash karna / explore karna.
- **Data Analysis** = Data ko samajhna.

Yani: **kisi bhi project mein model banane ya final decision lene se pehle, data ko achhi tarah dekhna, check karna aur samajhna.**

**Real-life example:** Aap ek naya ghar kharidne jaate hain. Aap seedha paise nahi dete. Pehle aap ghar ke andar jaate hain, chhat dekhte hain, pipes check karte hain, bijli dekhte hain. **Yeh "exploration" hai.** Data ke saath bhi hum yehi karte hain.

EDA mein hum yeh sawal poochte hain:

- Data mein kitni rows aur columns hain?
- Kya koi value missing hai?
- Kya koi record do dafa (duplicate) hai?
- Average kitna hai?
- Kya koi value bahut ajeeb (outlier) hai?
- Kaun se columns aapas mein related hain?

## 1.3 Data Ko Graph Mein Kyun Convert Karte Hain?

| Sirf Numbers Dekhna | Graph Dekhna |
|---|---|
| Dheere samajh aata hai | Jaldi samajh aata hai |
| Pattern nazar nahi aata | Pattern foran nazar aata hai |
| Outlier chhup jata hai | Outlier alag nazar aata hai |
| Dusron ko samjhana mushkil | Dusron ko samjhana asaan |

## 1.4 Python Libraries: Pandas, NumPy, Matplotlib, Seaborn

Soch lein ke aap ek **dukaan** chala rahe hain:

| Library | Dukaan Wali Misaal | Asal Kaam |
|---|---|---|
| **NumPy** | Calculator | Numbers par tez calculations, arrays |
| **Pandas** | Register / Excel sheet | Data ko table (rows aur columns) mein rakhna aur sambhalna |
| **Matplotlib** | Kagaz aur pencil | Graph ki buniyad banana, poora control |
| **Seaborn** | Ready-made design wali rangeen copy | Matplotlib ke upar bana hua, kam code mein khoobsurat statistical graphs |

```python
import numpy as np                 # NumPy ko np naam se import kiya
import pandas as pd                # Pandas ko pd naam se import kiya
import matplotlib.pyplot as plt    # Matplotlib ka pyplot hissa plt naam se
import seaborn as sns              # Seaborn ko sns naam se
```

**Line-by-line explanation:**

- `import numpy as np` → NumPy library ko program mein bulaya. `as np` ka matlab: "isay chhota naam `np` de do", taake baar baar `numpy` na likhna paray.
- `import pandas as pd` → Pandas bulaya aur chhota naam `pd` diya. Data tables ke liye.
- `import matplotlib.pyplot as plt` → Matplotlib ka `pyplot` module bulaya. `plt.show()`, `plt.title()` jaise functions yahin se aate hain.
- `import seaborn as sns` → Seaborn bulaya. `sns` is ka mash-hoor chhota naam hai.

## 1.5 Matplotlib Aur Seaborn Mein Farq

| Point | Matplotlib | Seaborn |
|---|---|---|
| Level | Low-level (bunyadi, har cheez khud set karo) | High-level (kam code mein tayyar graph) |
| Code ki length | Zyada | Kam |
| Default look | Saada | Khoobsurat |
| Statistical graphs | Khud calculate karna parta hai | Boxplot, violinplot, regplot, heatmap jaise graphs ready |
| Data input | Lists/arrays | DataFrame ke saath behtareen kaam |
| Control | Bohat zyada | Matplotlib ke zariye customize hota hai |

> **Yaad rakhein:** Seaborn, Matplotlib ke **upar** bana hai. Isi liye Seaborn ke graph ko customize karne ke liye hum `plt` (Matplotlib) ke functions bhi use karte hain. Dono dost hain, dushman nahi!

## 1.6 Zaroori Basic Terms

### DataFrame
**DataFrame** = Pandas ki **table** jis mein rows aur columns hote hain (bilkul Excel sheet ki tarah).

| student_name | study_hours | final_marks |
|---|---|---|
| Ali | 5.0 | 70 |
| Sana | 3.0 | 50 |

### Series
**Series** = DataFrame ka **ek akela column** (ya ek akeli row).

```python
df["final_marks"]   # yeh ek Series hai
```

### Row aur Column
- **Row** = Ek record. Misaal: ek student ka poora data.
- **Column** = Ek property. Misaal: sab students ke `final_marks`.

### x, y aur hue
Graph mein:
- **`x`** = Neeche wali (horizontal) axis par kaun sa column dikhana hai.
- **`y`** = Side wali (vertical) axis par kaun sa column dikhana hai.
- **`hue`** = Colors ke zariye **ek aur category** dikhana. Misaal: `hue="gender"` → Male alag color, Female alag color.

**Misaal:** "Study hours (x) ke mutabiq marks (y) dikhao, aur Male/Female ko alag rang (hue) do."

## 1.7 Categorical Aur Numerical Data

| Type | Matlab | Misalein | Graphs |
|---|---|---|---|
| **Numerical** | Aisa data jis par jama, minus, average ho sakta hai | `study_hours`, `math_marks`, `attendance` | Histogram, Scatter, Line, Box |
| **Categorical** | Aisa data jo categories/groups batata hai | `gender`, `class`, `city`, `passed` | Count plot, Bar plot |

**Chhoti si trick:** Agar aap us column ka *average* nikal sakte hain aur woh *meaningful* hai → Numerical. Agar nahi (jaise "city ka average") → Categorical.

> ⚠️ `student_id` numbers mein hai lekin yeh **sirf pehchan (ID)** hai. Is ka average meaningless hai. Isay numerical analysis mein shamil na karein.

## 1.8 Independent Aur Dependent Variables (Beginner Introduction)

- **Independent variable (X)** = Woh cheez jo hum **badalte ya observe karte** hain. Misaal: `study_hours`.
- **Dependent variable (Y)** = Woh cheez jo **pehli cheez par depend** kar sakti hai. Misaal: `final_marks`.

**Misaal:** "Zyada parhai karne se marks barhte hain?" → Study hours (independent), Marks (dependent).

Scatter plot mein aam tor par independent variable **x-axis** par aur dependent variable **y-axis** par rakhte hain.

## 1.9 Missing Values, Duplicates Aur Outliers

### Missing Values
Woh jagah jahan data **khali** hai (`NaN`). Misaal: kisi student ki attendance likhi hi nahi gayi.
**Masla:** Average aur graphs ghalat ho sakte hain.

### Duplicate Records
Ek hi record **do ya zyada baar** likha gaya. Misaal: "Ali Raza" ki poori row 2 baar aa gayi.
**Masla:** Count aur average ghalat ho jata hai.

### Outliers
Woh values jo baqi data se **bohat alag** hon. Misaal: Class ke zyadatar marks 40-80 hain, aur ek student ke 100 marks.

> ❗ **Har outlier ghalti nahi hota.** Ho sakta hai ek student sach mein bohat tez ho. Pehle **investigate** karein, phir faisla karein ke rakhna hai ya hatana.

## 1.10 Graph Select Karne Ka Sahi Tareeqa (Quick Idea)

Graph chunne se pehle **do sawal** poochein:

1. **Mera sawal kya hai?** (trend? comparison? relationship? distribution?)
2. **Mere columns kis type ke hain?** (numerical ya categorical?)

| Sawal | Graph (aam tor par) |
|---|---|
| Waqt ke saath kya badla? | Line plot |
| Kaun si category zyada/kam? | Bar plot |
| Do numbers ka relation? | Scatter plot |
| Data kaisa phaila hua hai? | Histogram |
| Median aur outliers? | Box plot |
| Kitne log har category mein? | Count plot |
| Kaun se columns related hain? | Heatmap |

> Yeh shortcuts hain, **absolute rules nahi**. Detail aage course ke end mein hai.

## 1.11 Installation (Windows, Step by Step)

### Step 1: Python check karein
Windows mein **Start Menu → "cmd" likhein → Enter** (Command Prompt khulega). Phir likhein:

```bash
python --version
```

**Matlab:** Python install hai ya nahi, aur kaun sa version hai. Output kuch aisa aayega: `Python 3.11.5`. Agar error aaye to https://www.python.org se Python download karein. Install karte waqt **"Add Python to PATH"** ka checkbox zaroor tick karein.

### Step 2: Libraries install karein

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

**Command ka matlab:**
- `pip` = Python ka **app-store** (packages install karne wala tool).
- `install` = Install karo.
- `pandas numpy matplotlib seaborn scikit-learn jupyter` = In sab libraries ke naam. Ek hi command mein sab install ho jayengi.
- `scikit-learn` = Machine learning library (is course mein zyada nahi, lekin aage kaam aati hai).
- `jupyter` = Notebook environment jahan code aur graph ek hi page par nazar aate hain.

Agar `pip` na chale, to try karein:

```bash
python -m pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Step 3: Versions check karein

```python
import pandas as pd
import numpy as np
import matplotlib
import seaborn as sns

print("pandas    :", pd.__version__)
print("numpy     :", np.__version__)
print("matplotlib:", matplotlib.__version__)
print("seaborn   :", sns.__version__)
```

**Explanation:**
- Pehli 4 lines libraries import karti hain.
- `pd.__version__` library ka version batata hai.
- `print("pandas    :", ...)` pehle ek label aur phir version dikhata hai.

> Is course ka code **Seaborn 0.13 ya us se naye version** ke liye likha gaya hai. Agar aap ka version bohat purana hai to upgrade karein: `pip install --upgrade seaborn`.

### Step 4: Jupyter Notebook chalana

```bash
jupyter notebook
```

- Browser mein ek page khulega.
- Right side par **New → Python 3 (ipykernel)** par click karein.
- Ek **cell** milega. Usmein code likhein aur **Shift + Enter** dabayein → code run hoga aur graph neeche nazar aayega.
- Agar graph nazar na aaye to ek cell mein yeh likh dein: `%matplotlib inline`

> **Agar aap Python file (`.py`) mein code chalate hain**, to graph dikhane ke liye har graph ke end par `plt.show()` likhna **zaroori** hai. Jupyter mein aksar graph khud nazar aa jata hai, lekin `plt.show()` likhna aadat banayein.

### Har Chapter Ka Standard Import Block

Is course mein har chapter ke shuru mein yeh imports aur data loading hogi:

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_theme(style="whitegrid")          # graph ka khoobsurat default style
df = pd.read_csv("student_performance.csv")  # CSV file load karo
```

---

# PART 2: Common Dataset — Student Performance

> 📌 **Dobara yaad dehani:** Yeh data **synthetic (banawati) practice data** hai jo `NumPy` ke random numbers se bana hai. Yeh kisi asal school ka record **nahi** hai.

## 2.1 Dataset Ke Columns

| Column | Type | Matlab |
|---|---|---|
| `student_id` | Number (ID) | Student ka unique number |
| `student_name` | Text | Student ka naam |
| `gender` | Categorical | Male / Female |
| `class` | Categorical | Class 8 / Class 9 / Class 10 |
| `study_hours` | Numerical | Roz kitne ghante parhta hai |
| `attendance` | Numerical | Attendance percentage (50 se 100) |
| `math_marks` | Numerical | Math ke marks (100 mein se) |
| `science_marks` | Numerical | Science ke marks |
| `english_marks` | Numerical | English ke marks |
| `final_marks` | Numerical | Weighted final marks |
| `passed` | Categorical | Pass / Fail |
| `city` | Categorical | Karachi / Lahore / Islamabad / Multan |

> **Note:** `class` Python ka ek **reserved keyword** hai, is liye hum isay `df["class"]` likh kar access karte hain (`df.class` likhna **error** dega).

## 2.2 Dataset Python Code Se Generate Karna

Is file ka naam rakhein: `create_dataset.py` (ya Jupyter ke ek cell mein chalayein).

```python
import numpy as np
import pandas as pd

np.random.seed(42)   # Har baar same random data aaye
n = 40               # Kitne students chahiye

names = [
    "Ali Raza", "Ayesha Khan", "Bilal Ahmed", "Fatima Noor", "Hamza Sheikh",
    "Sana Iqbal", "Usman Ghani", "Zainab Ali", "Hassan Raza", "Maryam Aslam",
    "Ahmed Khan", "Hira Malik", "Danish Mehmood", "Iqra Hussain", "Farhan Siddiqui",
    "Noor Fatima", "Saad Qureshi", "Amna Tariq", "Imran Baig", "Laiba Shah",
    "Taha Javed", "Rabia Anwar", "Zeeshan Haider", "Mehwish Akram", "Kamran Butt",
    "Sidra Parveen", "Waqas Mirza", "Anum Saleem", "Junaid Rauf", "Komal Riaz",
    "Adnan Farooq", "Samina Bibi", "Rizwan Ullah", "Khadija Nasir", "Shahzaib Ali",
    "Areeba Khalid", "Owais Memon", "Bushra Latif", "Talha Rehman", "Nimra Yousuf",
]
gender = ["Male", "Female", "Male", "Female", "Male", "Female", "Male", "Female", "Male", "Female"] * 4

classes = np.random.choice(["Class 8", "Class 9", "Class 10"], n)
cities = np.random.choice(["Karachi", "Lahore", "Islamabad", "Multan"], n, p=[0.35, 0.30, 0.20, 0.15])

study = np.round(np.random.uniform(1, 8, n), 1)
attendance = np.clip(np.round(60 + study * 3.5 + np.random.normal(0, 7, n)), 50, 100)

base = 25 + study * 7 + (attendance - 75) * 0.3
math = np.clip(np.round(base + np.random.normal(0, 7, n)), 5, 100)
science = np.clip(np.round(base + np.random.normal(0, 7, n)), 5, 100)
english = np.clip(np.round(base + 4 + np.random.normal(0, 6, n)), 5, 100)

df = pd.DataFrame({
    "student_id": range(1, n + 1),
    "student_name": names,
    "gender": gender,
    "class": classes,
    "study_hours": study,
    "attendance": attendance,
    "math_marks": math,
    "science_marks": science,
    "english_marks": english,
    "city": cities,
})

# Do jaan-boojh kar unusual (outlier) students:
df.loc[4, ["study_hours", "math_marks", "science_marks", "english_marks"]] = [1.0, 88, 85, 90]
df.loc[9, ["study_hours", "math_marks", "science_marks", "english_marks"]] = [8.0, 30, 28, 35]

df["final_marks"] = np.round(0.4 * df["math_marks"] + 0.3 * df["science_marks"] + 0.3 * df["english_marks"], 1)
df["passed"] = np.where(df["final_marks"] >= 40, "Pass", "Fail")

df = df[["student_id", "student_name", "gender", "class", "study_hours", "attendance",
         "math_marks", "science_marks", "english_marks", "final_marks", "passed", "city"]]

df.to_csv("student_performance.csv", index=False)
print("File save ho gayi! Shape:", df.shape)
```

### Line-by-line explanation

| Code | Matlab |
|---|---|
| `np.random.seed(42)` | Random numbers ko "lock" kar deta hai. Isse har student ko **wahi** data milega jo mujhe mila. `42` sirf ek number hai. |
| `n = 40` | Hum 40 students ka data banayenge. |
| `names = [...]` | 40 naamon ki list. |
| `gender = [...] * 4` | 10 genders ki list ko 4 baar repeat kiya = 40 values. |
| `np.random.choice([...], n)` | Diye gaye options mein se **random** 40 values chunta hai (har student ki class). |
| `p=[0.35, ...]` | Probability. Karachi ke students zyada (35%), Multan ke kam (15%). |
| `np.random.uniform(1, 8, n)` | 1 se 8 ke darmiyan 40 random decimal numbers (study hours). |
| `np.round(..., 1)` | Decimal ko 1 digit tak round karta hai (jaise 4.7). |
| `attendance = 60 + study*3.5 + noise` | Zyada parhne walon ki attendance thori behtar hoti hai, **lekin thora random farq** bhi (`np.random.normal(0, 7, n)` = "shor"/noise). |
| `np.clip(x, 50, 100)` | Values ko 50 se 100 ke andar rokta hai (attendance 100 se zyada nahi ho sakti). |
| `base = 25 + study*7 + ...` | Marks ki buniyad: study hours aur attendance ke saath marks barhte hain. **Yehi "reasonable relationship" hai.** |
| `math`, `science`, `english` | Base marks + thora random farq. English mein +4 ka bonus. |
| `pd.DataFrame({...})` | Dictionary se table bana rahe hain. Key = column name, value = us column ka data. |
| `df.loc[4, [...]] = [...]` | Row number 4 aur 9 ko manually badal kar do **unusual students** banaye. Student 5 ne 1 ghanta parha lekin marks bohat zyada. Student 10 ne 8 ghante parhe lekin marks kam. |
| `final_marks = 0.4*math + 0.3*science + 0.3*english` | Math ka 40%, Science ka 30%, English ka 30% weight. |
| `np.where(condition, "Pass", "Fail")` | Agar `final_marks >= 40` to "Pass", warna "Fail". |
| `df = df[[...]]` | Columns ko sahi tarteeb mein lagaya. |
| `df.to_csv("...", index=False)` | DataFrame ko CSV file mein save kiya. `index=False` = extra index column na likho. |

**Expected output:** `File save ho gayi! Shape: (40, 12)`

Ab aap ke folder mein `student_performance.csv` bangayi hai.

## 2.3 Dataset Load Karna Aur Pehli Nazar

```python
import pandas as pd

df = pd.read_csv("student_performance.csv")

print(df.head())
print(df.shape)
print(df.info())
print(df.describe())
```

**Line-by-line:**

- `import pandas as pd` → Pandas bulaya.
- `pd.read_csv("student_performance.csv")` → CSV file parh kar DataFrame bana diya. Agar file ka path ghalat hoga to `FileNotFoundError` aayega.
- `print(df.head())` → Pehli **5 rows** dikhata hai.
- `print(df.shape)` → `(rows, columns)` dikhata hai. Humare data mein `(40, 12)`.
- `print(df.info())` → Har column ka data type aur kitni values khali nahi hain.
- `print(df.describe())` → Numerical columns ka summary: count, mean, std, min, 25%, 50%, 75%, max.

## 2.4 Data Ko Check Karna Seekhein

### `head()` aur `tail()`

```python
print(df.head())      # pehli 5 rows
print(df.head(10))    # pehli 10 rows
print(df.tail())      # aakhri 5 rows
```
`head()` aur `tail()` se andaza hota hai ke data kaisa dikhta hai aur file theek tarah load hui ya nahi.

### `shape`

```python
print(df.shape)       # (40, 12)
print("Rows:", df.shape[0], "Columns:", df.shape[1])
```
`shape` ek tuple hai. `shape[0]` = rows, `shape[1]` = columns. (Yahan `()` nahi lagte, kyun ke yeh function nahi attribute hai.)

### `columns`

```python
print(df.columns)
print(list(df.columns))
```
Sab column names dikhata hai. **Graph banate waqt column ka naam bilkul same likhna hota hai** (capital/small letters aur spelling).

### `info()`

```python
df.info()
```
Har column ka **data type** aur **non-null count** batata hai. Agar `non-null` count 40 se kam ho, to us column mein missing values hain. `int64`, `float64` = numbers; `object` ya `str` = text (pandas ka naya version text ko `str` bhi dikha sakta hai).

### `describe()`

```python
print(df.describe())                    # sirf numerical columns
print(df.describe(include="all"))       # sab columns
```
Numerical columns ke liye count, mean (average), std (phailao), min, 25%, 50% (median), 75%, max dikhata hai.

### Missing values: `isnull().sum()`

```python
print(df.isnull().sum())
```
- `isnull()` → har cell ke liye True (khali) ya False (bhari).
- `.sum()` → True ko 1 ginta hai, yani har column mein kitni values khali hain.
- Agar sab `0` hain to missing values nahi hain.

### Duplicates: `duplicated().sum()`

```python
print(df.duplicated().sum())
```
Kitni rows poori tarah repeat hui hain. `0` = koi duplicate nahi.

### `value_counts()`

```python
print(df["class"].value_counts())
print(df["gender"].value_counts())
print(df["passed"].value_counts())
print(df["passed"].value_counts(normalize=True) * 100)   # percentage
```
Kisi bhi categorical column mein har category ki tadaad batata hai. `normalize=True` count ko fraction (0 se 1) mein badal deta hai, `* 100` se percentage ban jati hai.

### `mean()`, `median()`, `min()`, `max()`

```python
print("Average final marks :", df["final_marks"].mean())
print("Median final marks  :", df["final_marks"].median())
print("Sab se kam marks    :", df["final_marks"].min())
print("Sab se zyada marks  :", df["final_marks"].max())

print(df[["math_marks", "science_marks", "english_marks"]].mean())
print(df.groupby("class")["final_marks"].mean())
```
- `mean()` = average (jama karke tadaad se taqseem).
- `median()` = beech wali value (sab ko tarteeb se lagayen to bilkul beech mein jo aaye).
- `min()` / `max()` = sab se chhoti / sab se badi value.
- `groupby("class")["final_marks"].mean()` = **har class ka alag average**.

## 2.5 Graph Banane Se Pehle Data Check Karna Kyun Zaroori Hai?

**Misaal:** Aap kisi ko cheeni samajh kar namak chai mein daal dein to chai kharab hogi. Isi tarah **ghalat data par bana graph bhi ghalat story sunata hai.**

| Agar data check na karein | Kya hoga |
|---|---|
| Missing values | Graph mein kuch points ghayab ho sakte hain ya error aa sakta hai |
| Duplicates | Counts aur averages inflate (zyada) ho jate hain |
| Number text ban gaya (`"85"`) | Graph sahi nahi banega / error |
| Outlier mojood ho | Average ghalat tasveer dikhata hai |
| Column ka naam ghalat | `KeyError` |

> **Golden Rule:** *"Graph se pehle data ko samjho."*

---
# PART 3: Complete Graphs Course

> **Har chapter ka format (13 steps):** Kya hai → Kyun → Kab → Real-life example → Graph kaise read karein → Required data → Complete code → Line-by-line explanation → Output explanation → Common mistakes → Real project use → Practice task → Quiz.
>
> **Har chapter ke code ko akele chalane ke liye** pehle `student_performance.csv` bana lein (Section 2.2) aur Chapter 1 wali `monthly_performance.csv` bhi.

---

## Chapter 1: Line Plot — `sns.lineplot()`

### 1. Line Plot Kya Hai?
**Line plot** mein points ko **ek line se jorha** jata hai. Yeh dikhata hai ke koi cheez **ek ordered sequence** (aam tor par waqt) ke saath kaise **badal rahi** hai.

### 2. Kyun Use Hota Hai?
Taake hum **trend** dekh sakein: cheez **upar ja rahi hai, neeche aa rahi hai, ya sthir (stable) hai.**

### 3. Kab Use Hota Hai?
- Mahine ba mahine sales, marks ya temperature.
- Din ba din patients ki tadaad.
- Saal ba saal dakhla (admissions).

### 4. Real-Life Example
School ki principal dekhna chahti hain ke **January se June tak** har class ke average marks **barh rahe hain ya nahi.**

### 5. Graph Kaise Read Karein?
- **X-axis:** Waqt (Jan, Feb, Mar...).
- **Y-axis:** Jo cheez naap rahe hain (average marks).
- **Line ka upar jana:** Behtari (is example mein).
- **Line ka neeche aana:** Giravat.
- **Alag alag colors ki lines:** Alag groups (jaise alag classes).
- **Markers (chhote dot/circle):** Asal data points.

### 6. Required Data
- Ek **ordered column** (month, date, year) → `x`
- Ek **numerical column** → `y`
- Optional: ek **category column** (class) → `hue`

> ⚠️ Line plot **sirf tab** use karein jab x-axis par **koi natural order** ho (waqt wagaira). Hamare `student_performance.csv` mein **time column nahi hai**, is liye us par "mahino ka trend" banana **jhoot** hoga. Is liye hum ek **alag monthly dataset** banayenge.

### 7. Complete Code

**Step A: Monthly dataset banayein (synthetic practice data)**

```python
import pandas as pd

monthly = pd.DataFrame({
    "month": ["Jan", "Feb", "Mar", "Apr", "May", "Jun"] * 3,
    "class": ["Class 8"] * 6 + ["Class 9"] * 6 + ["Class 10"] * 6,
    "avg_marks": [52, 54, 57, 59, 63, 66,      # Class 8
                  48, 50, 49, 55, 58, 60,      # Class 9
                  55, 57, 60, 62, 61, 68],     # Class 10
})
monthly.to_csv("monthly_performance.csv", index=False)
print(monthly.head(8))
```

**Step B: Line plot**

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_theme(style="whitegrid")
monthly = pd.read_csv("monthly_performance.csv")

plt.figure(figsize=(8, 5))
sns.lineplot(
    data=monthly,
    x="month",
    y="avg_marks",
    hue="class",
    style="class",
    marker="o",
    errorbar=None,
)
plt.title("Monthly Average Marks by Class (Synthetic Data)")
plt.xlabel("Month")
plt.ylabel("Average Marks")
plt.tight_layout()
plt.show()
```

### 8. Line-by-Line Explanation

**Step A:**
- `pd.DataFrame({...})` → Dictionary se table banayi. Har key ek column hai.
- `["Jan", ..., "Jun"] * 3` → 6 mahino ki list ko 3 baar repeat kiya (har class ke liye ek baar) = 18 values.
- `["Class 8"] * 6 + ["Class 9"] * 6 + ...` → Har class ka naam 6 baar. Is tarah har row = "ek class, ek mahina".
- `avg_marks = [...]` → 18 marks (3 classes × 6 mahine).
- `monthly.to_csv(..., index=False)` → File save ki.

**Step B:**
- `sns.set_theme(style="whitegrid")` → Graph ka background saaf aur grid wala.
- `pd.read_csv(...)` → Monthly file load ki.
- `plt.figure(figsize=(8, 5))` → Graph ka size: 8 inch chora, 5 inch lamba.
- `sns.lineplot(` → Line plot function shuru.
- `data=monthly` → Data kahan se lena hai (DataFrame).
- `x="month"` → X-axis par mahine.
- `y="avg_marks"` → Y-axis par average marks.
- `hue="class"` → Har class ka **alag color** ki line.
- `style="class"` → Har class ki line ka **alag style** (solid, dashed). Black-and-white print mein bhi farq nazar aata hai.
- `marker="o"` → Har point par ek gol circle.
- `errorbar=None` → Error band (shaded area) band kar do. Humare paas har (month, class) ka sirf ek hi number hai, is liye band ki zaroorat nahi.
- `plt.title`, `xlabel`, `ylabel` → Graph ka naam aur axes ke labels.
- `plt.tight_layout()` → Cheezon ko overlap hone se bachata hai.
- `plt.show()` → Graph screen par dikhata hai.

**Parameters ka matlab:**

| Parameter | Matlab | Required? |
|---|---|---|
| `data` | DataFrame | Optional lekin column names use karne ke liye zaroori |
| `x`, `y` | Kaun se columns | Practically required |
| `hue` | Colors se group | Optional |
| `style` | Line/marker ka style se group | Optional |
| `marker` | Point ka nishan (`"o"`, `"s"`, `"^"`) | Optional |
| `errorbar` | Uncertainty band. `None` = band nahi, `("ci", 95)` = 95% confidence interval, `"sd"` = standard deviation | Optional. Default: confidence interval jab ek x par kai values hon |

### Agar ek x par kai values hon to?
Agar ek hi mahine mein kai students ke marks hon, to `lineplot` khud **average** nikal kar line banata hai aur **shaded band** (errorbar) dikhata hai. Band jitna chora, utni uncertainty.

```python
# Misaal: study_hours ko round karke group bana lein
df = pd.read_csv("student_performance.csv")
df["hours_group"] = df["study_hours"].round()      # 1.0, 2.0, ... 8.0

plt.figure(figsize=(8, 5))
sns.lineplot(data=df, x="hours_group", y="final_marks", marker="o", errorbar=("ci", 95))
plt.title("Average Final Marks by Study Hours (Rounded)")
plt.xlabel("Study Hours (rounded)")
plt.ylabel("Average Final Marks")
plt.tight_layout()
plt.show()
```

- `df["study_hours"].round()` → 4.7 ko 5.0, 2.3 ko 2.0 banata hai, taake kuch groups ban jayein.
- `errorbar=("ci", 95)` → Har group ke average ke aas paas 95% confidence interval ka shaded band.
- **Ehtiyat:** Yeh "waqt ka trend" nahi, balki **ordered groups ka trend** hai. Kam students wale groups ka band chora hoga, aur is par bohat zyada bharosa nahi karna.

### 9. Output Ki Explanation
- Pehle graph mein **teeno classes ki lines** mahine ke saath upar ja rahi hain, yani **performance behtar ho rahi hai** (is synthetic data mein).
- Class 9 ki line sab se neeche hai (Jan mein 48), lekin phir bhi barh rahi hai.
- Class 10 ki line May mein halka sa gir kar June mein phir upar gayi. **Chhote dips normal hote hain**, hum pooray trend ko dekhte hain.
- Dosre graph mein jaise jaise study hours barhte hain, average marks bhi barhte nazar aate hain.

### 10. Common Mistakes
| Ghalti | Sahi tareeqa |
|---|---|
| Un categories par line plot jinka koi order nahi (jaise cities) | Bar plot use karein |
| Months ko alphabetical order mein dikhana (Apr, Aug, Dec...) | Months ko sahi order mein rakhein ya numeric month use karein |
| Bohat kam points (2 points) par line | 2 points se trend ka dawa mushkil hai. Zyada data lein |
| Bohat zyada lines (10+) | Graph ulajh jata hai. Sirf zaroori groups dikhayein |
| Student-level data par bina group kiye line | Pehle aggregate (average) karein |

### 11. Real Project Use
- **Business:** Monthly sales trend, website visitors.
- **Hospital:** Haftawar patients ki tadaad.
- **Weather:** Din ba din temperature.
- **Stock/Finance:** Qeemat ka time series.

**Time-series data** wo data hota hai jo **waqt ke mutabiq record** ho (din, hafta, mahina, saal).

**Line plot vs Scatter plot:**

| Line Plot | Scatter Plot |
|---|---|
| Points ko line se jorta hai | Sirf alag alag dots |
| Order/trend important | Do variables ka relation important |
| X aksar waqt hota hai | X aur Y dono numbers |
| Sawal: "Kaise badla?" | Sawal: "Kya related hain?" |

**Line plot kab use na karein?** Jab x-axis par **order na ho** (cities, genders), ya jab aap ke paas **bohat kam points** hon, ya jab data ko line se jorna "beech ke ghalat tasur" de.

### 12. Practice Task
1. `monthly` data mein **Class 9** ka sirf alag line plot banayein (hint: `monthly[monthly["class"] == "Class 9"]`).
2. `marker="s"` aur `linewidth=3` try karein.
3. Ek naya column `avg_attendance` add karke dusra line plot banayein.

### 13. Quiz
1. Line plot sab se zyada kis liye hota hai? → **Waqt ke saath trend dekhne ke liye.**
2. `hue="class"` kya karta hai? → **Har class ki line ka alag color.**
3. Cities ko line se jorna kyun ghalat hai? → **Cities ka koi natural order nahi hota.**
4. `errorbar=None` ka matlab? → **Shaded uncertainty band nahi dikhana.**
5. Time-series data kya hota hai? → **Waqt ke mutabiq record kiya gaya data.**

---

## Chapter 2: Bar Plot — `sns.barplot()`

### 1. Bar Plot Kya Hai?
**Bar plot** mein har category ke liye ek **bar** hota hai. Bar ki **lambai** us category ki **summary value** (aam tor par **average**) dikhati hai.

### 2. Kyun Use Hota Hai?
**Categories ka aapas mein comparison** karne ke liye.

### 3. Kab Use Hota Hai?
- Class-wise average marks.
- City-wise average sales.
- Department-wise average salary.

### 4. Real-Life Example
Principal poochti hain: *"Class 8, 9 aur 10 mein se kis class ke average marks zyada hain? Boys ya girls?"*

### 5. Graph Kaise Read Karein?
- **X-axis:** Category (class).
- **Y-axis:** Average (ya koi aur summary) value.
- **Bar ki oonchai:** Jitna lamba, utni zyada value.
- **Bar ke upar kali line (error bar):** Average ki **uncertainty**. Chhoti line = zyada yaqeen, lambi line = kam yaqeen.

### 6. Required Data
- Ek **categorical column** (`class`, `gender`).
- Ek **numerical column** (`final_marks`).
- Optional: doosra categorical column `hue` ke liye.

### 7. Complete Code

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_theme(style="whitegrid")
df = pd.read_csv("student_performance.csv")

# ---- Graph 1: Class-wise average final marks ----
plt.figure(figsize=(7, 5))
sns.barplot(
    data=df,
    x="class",
    y="final_marks",
    order=["Class 8", "Class 9", "Class 10"],
    estimator="mean",
    errorbar=("ci", 95),
    hue="class",
    palette="Set2",
    legend=False,
)
plt.title("Average Final Marks by Class")
plt.xlabel("Class")
plt.ylabel("Average Final Marks")
plt.tight_layout()
plt.show()

# ---- Graph 2: Boys vs Girls ----
plt.figure(figsize=(6, 5))
sns.barplot(data=df, x="gender", y="final_marks", hue="gender",
            palette="pastel", errorbar=None, legend=False)
plt.title("Average Final Marks: Male vs Female")
plt.xlabel("Gender")
plt.ylabel("Average Final Marks")
plt.tight_layout()
plt.show()

# ---- Graph 3: Class aur gender dono ----
plt.figure(figsize=(8, 5))
sns.barplot(data=df, x="class", y="final_marks", hue="gender",
            order=["Class 8", "Class 9", "Class 10"], errorbar=None)
plt.title("Average Final Marks by Class and Gender")
plt.xlabel("Class")
plt.ylabel("Average Final Marks")
plt.legend(title="Gender")
plt.tight_layout()
plt.show()
```

### 8. Line-by-Line Explanation
- `sns.set_theme(style="whitegrid")` → Safed background, halki grid lines.
- `df = pd.read_csv(...)` → Data load.
- `plt.figure(figsize=(7, 5))` → Naya graph (7×5 inch).
- `sns.barplot(` → Bar plot shuru.
- `data=df` → Data DataFrame `df` se.
- `x="class"` → X-axis par class categories.
- `y="final_marks"` → Y-axis par marks (bar ki lambai average marks se banegi).
- `order=[...]` → Bars ki **tarteeb** khud tay ki (8, 9, 10). Agar na likhein to jis order mein data mein pehli baar aayi, usi order mein ban jayengi.
- `estimator="mean"` → Summary statistic average hai. Aap `"median"`, `"sum"`, `"max"` bhi de sakte hain. (`mean` default hai.)
- `errorbar=("ci", 95)` → Har bar par 95% confidence interval ki line. `errorbar=None` = line nahi.
- `hue="class", palette="Set2", legend=False` → Har bar ko alag color dene ka **naya tareeqa** (Seaborn 0.13). `palette` tabhi sahi chalta hai jab `hue` diya ho. Colors zahir hain is liye legend ki zaroorat nahi (`legend=False`).
- `plt.title/xlabel/ylabel` → Title aur labels.
- `plt.legend(title="Gender")` → Legend ka title set kiya.
- Graph 3 mein `hue="gender"` → Har class ke andar Male aur Female ke **do alag bars**.

**Parameters ki table:**

| Parameter | Matlab | Required? |
|---|---|---|
| `data` | DataFrame | Column names use karne ke liye zaroori |
| `x`, `y` | Category aur numerical column | Zaroori (ek category, ek numeric) |
| `hue` | Group ke andar sub-groups (color) | Optional |
| `order` | Bars ki tarteeb | Optional |
| `estimator` | Kaun si summary (mean/median/sum) | Optional (default mean) |
| `errorbar` | Uncertainty ki line | Optional |
| `palette` | Colors ka set | Optional (hue ke saath behtar) |

### 9. Output Ki Explanation
Hamare synthetic data ke mutabiq (approximately):
- **Class 10** ka average sab se zyada (~60.5), phir **Class 8** (~58.9), phir **Class 9** (~56.2).
- **Females** ka average (~60.0) **Males** (~57.6) se thora zyada hai.
- **Lekin dhyan dein:** Farq **chhota** hai aur sirf 40 students hain. Error bars bhi aapas mein overlap karte hain, is liye hum yeh nahi keh sakte ke "Class 10 pakka behtar hai". Hum sirf kehte hain **"is sample mein thora zyada hai."**

### 10. Common Mistakes
| Ghalti | Sahi |
|---|---|
| Samajhna ke bar = **total students** | Bar plot (numeric `y` ke saath) **average** dikhata hai, tadaad nahi. Tadaad ke liye `countplot` |
| `y` mein text column dena (`y="gender"`) | `y` numerical hona chahiye |
| Bar ka y-axis zero se shuru na karna | Bars ki lambai ka muqabla tabhi sahi hai jab axis **0 se shuru** ho |
| `palette` bina `hue` ke dena | `hue` bhi dein aur `legend=False` likhein |
| Bohat se categories (50+) | Top 10 chunein ya horizontal bar plot |

### 11. Real Project Use
- Department-wise average salary.
- Region-wise total sales (`estimator="sum"`).
- Product category ki average rating.

**Bar plot vs Count plot:**

| Bar Plot | Count Plot |
|---|---|
| `x` aur `y` dono dete hain | Sirf ek column dete hain |
| Bar ki oonchai = **average / sum** | Bar ki oonchai = **kitni baar aaya (count)** |
| Misaal: class-wise average marks | Misaal: class-wise student count |

### 12. Practice Task
1. City-wise average `final_marks` ka bar plot banayein.
2. Us mein `estimator="median"` lagayein, farq dekhein.
3. Horizontal bar plot banayein (`x="final_marks", y="city"`).

### 13. Quiz
1. Bar plot ki lambai kya dikhati hai? → **Aam tor par average (ya koi summary).**
2. `order` ka kaam? → **Bars ki tarteeb tay karna.**
3. Kya bar plot aur count plot ek hi hain? → **Nahi; count plot tadaad, bar plot summary dikhata hai.**
4. `estimator="sum"` kya karega? → **Average ke bajaye total dikhayega.**

---

## Chapter 3: Scatter Plot — `sns.scatterplot()`

### 1. Scatter Plot Kya Hai?
**Scatter plot** mein **har row ek dot** hoti hai. Dot ki position `x` aur `y` values se tay hoti hai.

### 2. Kyun Use Hota Hai?
**Do numerical variables ka relationship** dekhne ke liye.

### 3. Kab Use Hota Hai?
- Study hours vs marks.
- Advertisement ka kharcha vs sales.
- Umar vs blood pressure.

### 4. Real-Life Example
Aap janna chahte hain: *"Jo student zyada ghante parhta hai, kya us ke marks bhi zyada hote hain?"*

### 5. Graph Kaise Read Karein?
- **Har dot** = ek student.
- **X-axis:** Study hours. **Y-axis:** Final marks.
- Dots agar **neeche-left se upar-right** jayein → **Positive correlation** (ek barhe to doosra bhi barhe).
- Dots agar **upar-left se neeche-right** jayein → **Negative correlation** (ek barhe to doosra ghate).
- Dots agar **bikhre hue, koi shakal nahi** → **No correlation**.
- Jo dot baqiyon se **bohat door** ho → **Outlier**.

### 6. Required Data
Do **numerical columns** (`study_hours`, `final_marks`). Optional: `hue` (category ya number), `size` (number), `style` (category).

### 7. Complete Code

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_theme(style="whitegrid")
df = pd.read_csv("student_performance.csv")

# ---- Graph 1: Basic ----
plt.figure(figsize=(7, 5))
sns.scatterplot(data=df, x="study_hours", y="final_marks")
plt.title("Study Hours vs Final Marks")
plt.xlabel("Study Hours (per day)")
plt.ylabel("Final Marks")
plt.tight_layout()
plt.show()

# ---- Graph 2: Zyada information ----
plt.figure(figsize=(9, 6))
sns.scatterplot(
    data=df,
    x="study_hours",
    y="final_marks",
    hue="passed",
    style="gender",
    size="attendance",
    sizes=(40, 250),
    alpha=0.7,
)
plt.title("Study Hours vs Final Marks (Color=Result, Shape=Gender, Size=Attendance)")
plt.xlabel("Study Hours (per day)")
plt.ylabel("Final Marks")
plt.legend(bbox_to_anchor=(1.02, 1), loc="upper left")
plt.tight_layout()
plt.show()

# ---- Correlation number ----
print("Correlation:", round(df["study_hours"].corr(df["final_marks"]), 2))
```

### 8. Line-by-Line Explanation
- `sns.scatterplot(data=df, x="study_hours", y="final_marks")` → Basic scatter plot. Har student = ek dot.
- `hue="passed"` → Pass aur Fail ke dots **alag color** mein.
- `style="gender"` → Male aur Female ke dots **alag shape** mein.
- `size="attendance"` → Jis ki attendance zyada, us ka dot **bada**.
- `sizes=(40, 250)` → Sab se chhote dot ka size 40, sab se bade ka 250.
- `alpha=0.7` → Dots ko thora **transparent** banata hai (0 = bilkul ghayab, 1 = bilkul thos). Jab dots ek doosre par aayein to nazar aata hai.
- `plt.legend(bbox_to_anchor=(1.02, 1), loc="upper left")` → Legend ko graph se **bahar** (right side) rakha taake dots ko na dhake.
- `df["study_hours"].corr(df["final_marks"])` → Do columns ka **correlation number** (-1 se +1).
- `round(..., 2)` → 2 decimal tak.

| Parameter | Matlab | Required? |
|---|---|---|
| `x`, `y` | Do numerical columns | Zaroori |
| `hue` | Color se group | Optional |
| `size` | Dot ka size kisi column se | Optional |
| `style` | Dot ki shape kisi category se | Optional |
| `alpha` | Transparency (0 se 1) | Optional |

### 9. Output Ki Explanation
- Dots **neeche-left se upar-right** ja rahe hain → **Positive relationship**. Correlation lagbhag **0.67** hai (moderate-to-strong positive).
- **Fail** wale zyadatar dots **neeche** (kam study hours) mein hain.
- **Do unusual dots** nazar aate hain: ek student (Hamza Sheikh) ne **sirf 1 ghanta** parha lekin marks **~88**; doosri student (Maryam Aslam) ne **8 ghante** parhe lekin marks **~31**. Yeh **outliers (relationship ke hisaab se)** hain. Hum inhein **error** nahi kehte; pehle wajah dhoondhte hain (shayad pehle se tez tha, shayad tabiyat kharab thi).

### Correlation Aur Causation
**Correlation** = Do cheezein **saath saath** badalti hain.
**Causation** = Ek cheez doosri ko **paida (cause)** karti hai.

**Misaal:** Garmiyon mein ice-cream ki sale aur dariya mein doobne ke waqiyat dono barhte hain. Is ka matlab **ice-cream khana doobne ki wajah nahi**. Teesri cheez **garmi** dono ki wajah hai.

> Hamare data mein study hours aur marks ka rishta hai, lekin **sirf scatter plot se hum "pakka" nahi keh sakte** ke study hours hi marks ki wajah hain. (Mumkin hai ke tez students zyada parhte bhi hon.)

### 10. Common Mistakes
| Ghalti | Sahi |
|---|---|
| Correlation ko causation samajhna | "Related hain" kahein, "wajah hai" nahi |
| Categorical column ko `x`/`y` banana | Scatter ke liye numerical columns |
| Bohat zyada `hue`, `size`, `style` ek saath | Graph ulajh jata hai; zaroorat ke mutabiq |
| Overlapping dots na dekhna | `alpha=0.6` lagayein |
| Outlier ko bina soche delete karna | Pehle wajah investigate karein |

### 11. Real Project Use
- Ad spend vs sales.
- House area vs price.
- Feature selection se pehle relationship dekhna (Machine Learning).

### 12. Practice Task
1. `attendance` vs `final_marks` ka scatter plot banayein.
2. `hue="class"` lagayein.
3. Outlier students ke naam dhoondhein: `df[(df["study_hours"] < 2) & (df["final_marks"] > 80)]`

### 13. Quiz
1. Scatter plot mein ek dot kya hai? → **Ek row/ek record.**
2. Positive correlation kya hai? → **Ek barhe to doosra bhi barhe.**
3. `alpha` kya karta hai? → **Transparency.**
4. Correlation = Causation? → **Nahi.**
5. Outlier kya hota hai? → **Baqi data se bohat alag value.**

---

## Chapter 4: Histogram — `sns.histplot()`

### 1. Histogram Kya Hai?
**Histogram** ek numerical column ko **chhote chhote dabbon (bins)** mein baant kar dikhata hai ke har dabbe mein **kitni values** hain.

### 2. Kyun Use Hota Hai?
Data ki **distribution** (phailao) samajhne ke liye: zyadatar values kahan hain? Kya data ek taraf jhuka hua hai?

### 3. Kab Use Hota Hai?
- Marks kis range mein zyada hain?
- Customers ki umar ka phailao.
- Patients ke waiting time.

### 4. Real-Life Example
Teacher dekhna chahti hain: *"Final marks mein kitne students 40-50 mein hain, kitne 50-60 mein, kitne 60-70 mein?"*

### 5. Graph Kaise Read Karein?
- **X-axis:** Marks ki range (bins).
- **Y-axis:** Frequency (kitne students us range mein).
- **Bar ki oonchai:** Us range mein zyada students.
- **Bars ke beech gap nahi hota** kyun ke numerical range continuous hoti hai.

### 6. Required Data
Sirf **ek numerical column**.

### Distribution Ki Shaklein
- **Approximately normal:** Beech mein zyada, dono taraf barabar kam (ghanti jaisi shakal).
- **Right-skewed (positive skew):** Zyadatar values chhoti, ek lambi **dum right** taraf.
- **Left-skewed (negative skew):** Zyadatar values barhi, ek lambi **dum left** taraf.

### Bins Kya Hain?
**Bin** = ek dabba/range, jaise 40 se 50 tak. Bohat kam bins → tafseel gum. Bohat zyada bins → graph kharab/ghair-wazeh. Bins ki tadaad data ke mutabiq tay karein.

### 7. Complete Code

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_theme(style="whitegrid")
df = pd.read_csv("student_performance.csv")

# ---- Graph 1: Basic ----
plt.figure(figsize=(7, 5))
sns.histplot(data=df, x="final_marks", bins=8, kde=True, color="steelblue")
plt.title("Distribution of Final Marks")
plt.xlabel("Final Marks")
plt.ylabel("Number of Students")
plt.tight_layout()
plt.show()

# ---- Graph 2: Bin width khud tay karein, percentage mein ----
plt.figure(figsize=(7, 5))
sns.histplot(data=df, x="final_marks", binwidth=10, stat="percent")
plt.title("Final Marks Distribution (Percent of Students)")
plt.xlabel("Final Marks")
plt.ylabel("Percent of Students (%)")
plt.tight_layout()
plt.show()

# ---- Graph 3: Pass aur Fail ka muqabla ----
plt.figure(figsize=(8, 5))
sns.histplot(data=df, x="final_marks", hue="passed", binwidth=10,
             element="step", multiple="layer")
plt.title("Final Marks Distribution: Pass vs Fail")
plt.xlabel("Final Marks")
plt.ylabel("Number of Students")
plt.tight_layout()
plt.show()

print("Skewness:", round(df["final_marks"].skew(), 2))
```

### 8. Line-by-Line Explanation
- `sns.histplot(data=df, x="final_marks", ...)` → `final_marks` ki distribution. Dhyan dein: histogram mein **sirf ek axis** (x) deta hain; y-axis khud count banta hai.
- `bins=8` → Data ko **8 dabbon** mein baanta.
- `kde=True` → Histogram ke upar ek **smooth curve** (KDE = Kernel Density Estimate) bhi. KDE bas "histogram ka naram (smooth) version" hai.
- `color="steelblue"` → Bars ka rang.
- `binwidth=10` → Har bin ki **chorai 10 marks**. (`bins` aur `binwidth` ek saath nahi dete; ek chunein.)
- `stat="percent"` → Y-axis par count ke bajaye **percentage**. Doosri options: `"count"` (default), `"frequency"`, `"density"`, `"probability"`.
- `hue="passed"` → Pass aur Fail ke liye alag colors.
- `element="step"` → Bars ke bajaye **sirf outline (step)**. Options: `"bars"` (default), `"step"`, `"poly"`.
- `multiple="layer"` → Dono groups ek ke upar ek (overlay). Options: `"layer"`, `"stack"`, `"dodge"`, `"fill"`.
- `df["final_marks"].skew()` → Skewness number. **Negative** = left-skewed, **positive** = right-skewed, **0 ke qareeb** = lagbhag symmetric.

| Parameter | Matlab | Required? |
|---|---|---|
| `x` (ya `y`) | Ek numerical column | Zaroori |
| `bins` | Dabbon ki tadaad | Optional |
| `binwidth` | Har dabbe ki chorai | Optional |
| `kde` | Smooth curve | Optional (default False) |
| `stat` | Count / percent / density | Optional |
| `element` | Bars ki shakal | Optional |
| `hue` | Groups | Optional |

### 9. Output Ki Explanation
- Final marks ka skewness lagbhag **-0.23**, yani distribution **halki si left-skewed** hai. Sab se zyada students (40 mein se 18) 50 se 70 marks ke darmiyan hain, aur kuch kam marks wale students left taraf ek dum banate hain.
- **Fail** students (marks < 40) histogram ke **bilkul left** mein hain.
- Bohat zyada marks (80+) walay chand hi students hain.

### 10. Common Mistakes
| Ghalti | Sahi |
|---|---|
| Bar plot aur histogram ko ek samajhna | Histogram **numeric range**, bar plot **categories** |
| `bins` ko ek hi value par chhor dena aur result na dekhna | 5, 8, 10 try karke dekhein |
| Categorical column par histogram | Count plot use karein |
| `bins` aur `binwidth` dono dena | Ek hi chunein |
| Chhote data par KDE par zyada bharosa | 40 rows mein KDE andaza hai, sachai nahi |

**Histogram vs Bar plot:**

| Histogram | Bar Plot |
|---|---|
| Ek numerical column ko ranges mein baanta | Categories compare karta |
| Bars ke beech gap nahi | Bars ke beech gap |
| Y = frequency | Y = average/sum |

### 11. Real Project Use
- Customer age distribution.
- Delivery time analysis.
- Model ke errors ki distribution.
- Outlier aur skew ka pehla andaza.

### 12. Practice Task
1. `attendance` ka histogram banayein.
2. `bins=5`, `bins=15` try karke farq dekhein.
3. Teeno subjects (math, science, english) ke histograms banayein.

### 13. Quiz
1. Histogram kis cheez ko dikhata hai? → **Distribution.**
2. Bin kya hai? → **Marks ki ek range ka dabba.**
3. `kde=True` kya dega? → **Smooth curve.**
4. Left-skewed matlab? → **Lambi dum left taraf (kam values taraf).**
5. Histogram aur bar plot mein farq? → **Histogram numeric ranges, bar plot categories.**

---

## Chapter 5: Box Plot — `sns.boxplot()`

### 1. Box Plot Kya Hai?
**Box plot** (box-and-whisker plot) **5 important numbers** ek chhote se graph mein dikhata hai: minimum (whisker), Q1, median (Q2), Q3, maximum (whisker), aur **outlier points** alag.

### 2. Kyun Use Hota Hai?
- Data ka **markaz (median)** aur **phailao (spread)** dekhne ke liye.
- **Potential outliers** pehchaanne ke liye.
- **Groups ka muqabla** karne ke liye.

### 3. Kab Use Hota Hai?
Jab aap ko groups ki distribution ka tezi se muqabla karna ho (class-wise, city-wise).

### 4. Real-Life Example
Ek class ke 9 students ke marks tarteeb se: `35, 42, 48, 50, 55, 58, 62, 70, 100`

### Zero Se Samjhein: Median, Quartiles, IQR

**Median (Q2)** = Beech wali value. 9 values mein 5vi value = **55**.

**Q1 (25th percentile)** = Neeche ke 25% students is value se neeche hain = **48**.
**Q3 (75th percentile)** = 75% students is value se neeche = **62**.

**IQR (Interquartile Range)** = Q3 − Q1 = 62 − 48 = **14**. Yani **beech ke 50% students** ke marks 14 marks ki range mein hain.

> Note: Quartiles nikalne ke kai tareeqay hote hain. Pandas/NumPy ka tareeqa (linear interpolation) humne yahan use kiya hai. Doosre tareeqon se thora sa farq aa sakta hai. Yeh theek hai.

**Whiskers aur Outliers (1.5 × IQR rule):**
- Lower fence = Q1 − 1.5 × IQR = 48 − 21 = **27**
- Upper fence = Q3 + 1.5 × IQR = 62 + 21 = **83**
- Jo value **27 se kam ya 83 se zyada** ho, woh **outlier point** ke tor par alag dot mein dikhegi.
- Yahan **100** > 83, is liye **100 potential outlier** hai. 35 aur 42 fences ke andar hain.
- **Whisker** = box se nikalne wali line jo fence ke andar sab se door ki value tak jati hai.

Code se verify:

```python
import numpy as np

marks = [35, 42, 48, 50, 55, 58, 62, 70, 100]
q1, q2, q3 = np.percentile(marks, [25, 50, 75])
iqr = q3 - q1

print("Q1:", q1, "Median:", q2, "Q3:", q3)
print("IQR:", iqr)
print("Lower fence:", q1 - 1.5 * iqr)
print("Upper fence:", q3 + 1.5 * iqr)
```

- `np.percentile(marks, [25, 50, 75])` → Ek hi baar mein Q1, median, Q3 nikalta hai.
- `iqr = q3 - q1` → Beech ke 50% ka phailao.
- Akhri 2 lines outlier ki hadein (fences) nikalti hain.
- **Output:** Q1: 48.0, Median: 55.0, Q3: 62.0, IQR: 14.0, Lower fence: 27.0, Upper fence: 83.0

### 5. Graph Kaise Read Karein?
```
        o      <- outlier point (agar ho)
        |
      -----    <- upper whisker
        |
     |-----|   <- Q3
     |  -  |   <- median (beech ki line)
     |-----|   <- Q1
        |
      -----    <- lower whisker
```
- **Box** = beech ke 50% students (Q1 se Q3).
- **Box ke andar line** = median.
- **Whiskers** = baqi "normal" data.
- **Alag dots** = potential outliers.
- **Box jitna lamba** = data utna zyada phaila hua.

### 6. Required Data
Ek numerical column (aur optional: ek categorical column groups ke liye).

### 7. Complete Code

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_theme(style="whitegrid")
df = pd.read_csv("student_performance.csv")

# ---- Graph 1: Ek akela box plot ----
plt.figure(figsize=(5, 6))
sns.boxplot(data=df, y="final_marks", color="lightblue")
plt.title("Box Plot of Final Marks")
plt.ylabel("Final Marks")
plt.tight_layout()
plt.show()

# ---- Graph 2: Class-wise comparison ----
plt.figure(figsize=(8, 6))
sns.boxplot(
    data=df,
    x="class",
    y="final_marks",
    order=["Class 8", "Class 9", "Class 10"],
    hue="class",
    palette="Set2",
    legend=False,
)
plt.title("Final Marks by Class")
plt.xlabel("Class")
plt.ylabel("Final Marks")
plt.tight_layout()
plt.show()

# ---- Graph 3: Outliers ko manually check karna ----
q1 = df["final_marks"].quantile(0.25)
q3 = df["final_marks"].quantile(0.75)
iqr = q3 - q1
low = q1 - 1.5 * iqr
high = q3 + 1.5 * iqr
outliers = df[(df["final_marks"] < low) | (df["final_marks"] > high)]
print("Lower fence:", round(low, 2), "Upper fence:", round(high, 2))
print("Outliers ki tadaad:", len(outliers))
```

### 8. Line-by-Line Explanation
- `sns.boxplot(data=df, y="final_marks")` → Sirf `y` diya, is liye ek akela vertical box.
- `color="lightblue"` → Box ka rang.
- `x="class"` → Har class ke liye alag box.
- `order=[...]` → Boxes ki tarteeb.
- `hue="class", palette="Set2", legend=False` → Har class ko alag color (modern syntax).
- `df["final_marks"].quantile(0.25)` → Q1.
- `quantile(0.75)` → Q3.
- `iqr = q3 - q1` → IQR.
- `low`, `high` → Outlier ki hadein.
- `df[(...) | (...)]` → Woh rows jo `low` se kam **ya** `high` se zyada hain. `|` ka matlab "ya". Har condition ko `()` mein likhna zaroori hai.
- `len(outliers)` → Kitne outliers mile.

| Parameter | Matlab | Required? |
|---|---|---|
| `data`, `x`/`y` | Data aur columns | Kam az kam ek numerical axis zaroori |
| `hue` | Sub-groups | Optional |
| `order` | Boxes ki tarteeb | Optional |
| `palette` | Colors | Optional |
| `showfliers` | Outlier points dikhana ya nahi (default True) | Optional |
| `width` | Box ki chorai | Optional |

### 9. Output Ki Explanation
- Poore dataset ka `final_marks` median lagbhag **62.2** hai, Q1 ~ **46.3**, Q3 ~ **69.1**, yani **IQR ≈ 22.8**.
- 1.5×IQR rule ki hadein lagbhag **12.1** aur **103.4** hain. Koi bhi student in se bahar nahi, is liye **final_marks mein koi box-plot outlier nahi mila.**
- **Dilchasp baat:** Hamare do unusual students (Hamza aur Maryam) **final_marks ke hisaab se outlier nahi** hain. Woh **study_hours ke rishte** ke hisaab se unusual hain jo scatter plot mein nazar aaye. Is liye **ek graph kafi nahi, kai graphs se data dekhna chahiye.**
- Teeno classes ke **median** (Class 8 ~56.7, Class 9 ~62.2, Class 10 ~66.9) alag alag hain. Class 10 ka median sab se zyada hai (jabke average mein bhi Class 10 upar tha).
- **Boxes ka phailao** classes mein alag hai, matlab kisi class mein marks zyada phaile hue hain.

### 10. Common Mistakes
| Ghalti | Sahi |
|---|---|
| Har outlier ko "error" samajh kar delete kar dena | Pehle wajah dekhein: data entry ghalti? ya asal unusual value? |
| Box ke andar ki line ko average samajhna | Woh **median** hai |
| Box plot ko bohat kam data par use karna (5-6 rows) | Kam az kam 15-20 points behtar hain |
| Categorical column ko `y` dena | `y` numerical hona chahiye |
| Q1/Q3 ko min/max samajhna | Box ke kinare Q1 aur Q3 hain, min/max nahi |

### 11. Real Project Use
- Salary distribution department-wise.
- Delivery time ka outlier detection.
- Lab test results ka comparison.

### 12. Practice Task
1. `city` ke mutabiq `final_marks` ka box plot.
2. `gender` aur `class` dono ke saath (`hue="gender"`).
3. `attendance` ka outlier check (IQR rule se).

### 13. Quiz
1. Box ke andar ki line kya hai? → **Median.**
2. IQR ka formula? → **Q3 − Q1.**
3. Whisker ke bahar dots kya hain? → **Potential outliers.**
4. Kya har outlier ghalti hota hai? → **Nahi.**
5. Marks `[10, 20, 30, 40, 50]` ka median? → **30.**

---

## Chapter 6: Count Plot — `sns.countplot()`

### 1. Count Plot Kya Hai?
**Count plot** ek **categorical column** ki **har category ki tadaad** (kitni baar aayi) bar se dikhata hai.

### 2. Kyun Use Hota Hai?
Jaanne ke liye: *"Har category mein kitni rows / kitne log hain?"*

### 3. Kab Use Hota Hai?
- Pass/Fail students ki tadaad.
- Har city ke customers.
- Hospital mein har department ke patients.

### 4. Real-Life Example
*"Kitne students pass hue aur kitne fail?"*

### 5. Graph Kaise Read Karein?
- **X-axis:** Category (`Pass`, `Fail`).
- **Y-axis:** Count (tadaad).
- **Bar ki oonchai:** Us category mein kitni rows.

### 6. Required Data
Sirf **ek categorical column**. Optional: `hue` ke liye doosra categorical column.

### 7. Complete Code

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_theme(style="whitegrid")
df = pd.read_csv("student_performance.csv")

# ---- Graph 1: Pass vs Fail ----
plt.figure(figsize=(6, 5))
ax = sns.countplot(data=df, x="passed", order=["Pass", "Fail"],
                   hue="passed", palette={"Pass": "seagreen", "Fail": "tomato"},
                   legend=False)
ax.bar_label(ax.containers[0])      # bar ke upar number
ax.bar_label(ax.containers[1])
plt.title("Number of Pass and Fail Students")
plt.xlabel("Result")
plt.ylabel("Number of Students")
plt.tight_layout()
plt.show()

# ---- Graph 2: Gender-wise student count ----
plt.figure(figsize=(6, 5))
sns.countplot(data=df, x="gender", hue="gender", palette="pastel", legend=False)
plt.title("Students by Gender")
plt.xlabel("Gender")
plt.ylabel("Number of Students")
plt.tight_layout()
plt.show()

# ---- Graph 3: Class ke andar pass/fail ----
plt.figure(figsize=(8, 5))
sns.countplot(data=df, x="class", hue="passed",
              order=["Class 8", "Class 9", "Class 10"])
plt.title("Pass/Fail Count by Class")
plt.xlabel("Class")
plt.ylabel("Number of Students")
plt.legend(title="Result")
plt.tight_layout()
plt.show()

# ---- Graph 4: Count nahi, percentage ----
plt.figure(figsize=(6, 5))
sns.countplot(data=df, x="passed", order=["Pass", "Fail"], stat="percent",
              hue="passed", legend=False)
plt.title("Pass vs Fail (Percent)")
plt.xlabel("Result")
plt.ylabel("Percent of Students (%)")
plt.tight_layout()
plt.show()
```

### 8. Line-by-Line Explanation
- `sns.countplot(data=df, x="passed")` → `passed` column ki har value ki tadaad. **`y` nahi dete**, kyun ke Seaborn khud count nikalta hai.
- `order=["Pass", "Fail"]` → Bars ki tarteeb.
- `hue="passed"` + `palette={...}` → Har category ko apna rang (dictionary: category → color).
- `legend=False` → Legend nahi (colors pehle se x-axis par likhe hain).
- `ax = sns.countplot(...)` → Seaborn `ax` (axes) wapas karta hai; us par hum aur cheezein lagate hain.
- `ax.bar_label(ax.containers[0])` → Pehle bar ke upar number likhta hai. Jab `hue` ho to har hue ka alag container hota hai (is liye `containers[0]` aur `[1]`).
- Graph 3 mein `x="class", hue="passed"` → har class ke andar Pass aur Fail ke 2 alag bars.
- `stat="percent"` → Count ke bajaye **percentage** dikhata hai (Seaborn 0.13+). Options: `"count"`, `"percent"`, `"proportion"`, `"probability"`.
- `plt.legend(title="Result")` → Legend ka title.

| Parameter | Matlab | Required? |
|---|---|---|
| `x` **ya** `y` | Categorical column (ek hi dein) | Zaroori |
| `data` | DataFrame | Zaroori (column names ke liye) |
| `hue` | Sub-groups | Optional |
| `order` | Tarteeb | Optional |
| `stat` | count/percent | Optional (default count) |

> `y="passed"` dene se **horizontal** bars banengi. `x` aur `y` dono ek saath na dein.

### 9. Output Ki Explanation
- **33 students Pass** aur **7 Fail** hain (is synthetic data mein). Yani lagbhag **82.5% pass** aur **17.5% fail**.
- Class-wise fail count: Class 8 mein 1, Class 9 mein 3, Class 10 mein 3. **Lekin dhyan dein:** Class 10 mein students zyada hain (17), is liye sirf count dekh kar na kahein "Class 10 kharab hai". **Percentage** dekhna behtar hai (Class 10: 3/17 ≈ 17.6%, Class 9: 3/12 = 25%, Class 8: 1/11 ≈ 9.1%).
- Gender: 20 Male aur 20 Female (barabar). Pass/Fail mein Female: 17 Pass, 3 Fail; Male: 16 Pass, 4 Fail.

**Counts vs Percentages:**
| Counts | Percentages |
|---|---|
| Asal tadaad batate hain | Muqabla fair banate hain jab group sizes alag hon |
| "3 fail" | "3 mein se 17 = 17.6%" |

### 10. Common Mistakes
| Ghalti | Sahi |
|---|---|
| `countplot` mein `x` aur `y` dono dena | Sirf ek dein |
| Numerical continuous column par countplot (`final_marks`) | Histogram use karein |
| Alag sizes ke groups ko sirf count se compare karna | Percentage bhi dekhein |
| `bar_label` ke liye `containers` ka ghalat index | Jitne `hue` utne containers |

**Bar plot vs Count plot:** Bar plot = kisi numeric column ka average (ya summary). Count plot = sirf tadaad.

### 11. Real Project Use
- Customer churn (gaye hue/rehne wale) ki ginti.
- Product category ke orders.
- Class imbalance check (machine learning mein: kya ek category bohat zyada hai?).

### 12. Practice Task
1. `city` ka count plot, bars ko zyada se kam tarteeb mein (hint: `order=df["city"].value_counts().index`).
2. `class` ke andar `gender` ka count plot.
3. Horizontal count plot banayein (`y="city"`).

### 13. Quiz
1. Count plot kya dikhata hai? → **Category ki tadaad.**
2. Kya count plot mein `y` dena zaroori hai? → **Nahi.**
3. `stat="percent"` ka matlab? → **Tadaad ke bajaye percentage.**
4. Bar plot aur count plot mein farq? → **Bar plot average, count plot tadaad.**

---
## Chapter 7: Heatmap — `sns.heatmap()`

### 1. Heatmap Kya Hai?
**Heatmap** ek **rangeen table** hai. Har **cell** ka **color** us cell ki **value** ke mutabiq hota hai. Zyada value = gehra ek rang, kam value = doosra rang.

### 2. Kyun Use Hota Hai?
Bohat saare numbers ko **ek nazar** mein samajhne ke liye. Khaas tor par **correlation matrix** dikhane ke liye.

### 3. Kab Use Hota Hai?
- Kaun se numerical columns aapas mein related hain?
- Din aur ghante ke hisaab se patients ki tadaad.
- Machine learning se pehle features ka relationship.

### 4. Real-Life Example
Aap janna chahte hain: *"Study hours, attendance, math, science, english aur final marks mein se kaun sa column kis se zyada related hai?"* 6 columns ka aapas mein muqabla = 6×6 table. Isay rang se dikhana heatmap hai.

### 5. Graph Kaise Read Karein?
- **Rows aur columns** dono mein **wahi variables**.
- **Har cell** = do variables ka **correlation**.
- **Correlation ki range: -1 se +1**
  - **+1** = mukammal positive (ek barhe to doosra bhi barabar barhe).
  - **0** = koi seedha (linear) rishta nahi.
  - **-1** = mukammal negative (ek barhe to doosra ghate).
- **Diagonal** (upar-left se neeche-right) par hamesha **1.00** hota hai, kyun ke har variable apne aap se mukammal related hota hai.
- **Rang:** `coolwarm` mein **laal = positive**, **neela = negative**, **safed/halka = 0 ke qareeb**.

**Correlation ko kaise samjhein (aam rule of thumb, strict rule nahi):**

| Value | Matlab |
|---|---|
| 0.7 se 1.0 | Strong positive |
| 0.4 se 0.7 | Moderate positive |
| 0.1 se 0.4 | Weak positive |
| -0.1 se 0.1 | Lagbhag koi linear rishta nahi |
| Negative values | Wahi sizes, lekin ulta (ek barhe to doosra ghate) |

> ⚠️ **Correlation causation nahi hota.** Correlation sirf **linear rishte** ko naapta hai; kabhi kabhi rishta curve jaisa ho to correlation kam aata hai.

### 6. Required Data
Ek **numerical DataFrame** (sirf numeric columns). Text columns (`gender`, `city`) is mein shamil na karein, warna error aa sakta hai.

### 7. Complete Code

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("student_performance.csv")

# Step 1: Sirf kaam ke numerical columns chunein
cols = ["study_hours", "attendance", "math_marks",
        "science_marks", "english_marks", "final_marks"]
numeric_df = df[cols]

# Step 2: Correlation matrix
corr = numeric_df.corr()
print(corr.round(2))

# Step 3: Basic heatmap
plt.figure(figsize=(8, 6))
sns.heatmap(corr, annot=True, cmap="coolwarm", fmt=".2f")
plt.title("Correlation Heatmap")
plt.tight_layout()
plt.show()

# Step 4: Behtar heatmap (mask, vmin/vmax, linewidths)
mask = np.triu(np.ones_like(corr, dtype=bool))     # upar ka hissa chhupao

plt.figure(figsize=(8, 6))
sns.heatmap(
    corr,
    mask=mask,
    annot=True,
    fmt=".2f",
    cmap="coolwarm",
    vmin=-1,
    vmax=1,
    linewidths=0.5,
    square=True,
)
plt.title("Correlation Heatmap (Lower Triangle)")
plt.tight_layout()
plt.show()
```

Aap `df.select_dtypes(include="number")` bhi use kar sakte hain, lekin us mein `student_id` bhi aa jayega (jo sirf ID hai). Is liye behtar hai ke `student_id` ko hata dein:

```python
numeric_df = df.select_dtypes(include="number").drop(columns="student_id")
corr = numeric_df.corr()
sns.heatmap(corr, annot=True, cmap="coolwarm", fmt=".2f")
```

### 8. Line-by-Line Explanation
- `cols = [...]` → Un columns ki list jin ka correlation dekhna hai.
- `numeric_df = df[cols]` → Sirf wahi columns ka naya DataFrame.
- `corr = numeric_df.corr()` → **Correlation matrix** banati hai (har column ka har doosre column se correlation). Yeh 6×6 table hogi.
- `corr.round(2)` → 2 decimal tak.
- `sns.heatmap(corr, ...)` → Correlation matrix ko heatmap mein badalta hai.
- `annot=True` → Har cell mein **number likha dikhao**. (`False` = sirf rang.)
- `cmap="coolwarm"` → **Color map**: neela se laal. Doosre options: `"viridis"`, `"Blues"`, `"RdBu_r"`.
- `fmt=".2f"` → Numbers ka format: 2 decimal (jaise 0.67).
- `np.triu(np.ones_like(corr, dtype=bool))` → Ek matrix jis ka **upar ka triangle True** hai. `np.ones_like` = corr jaisi shape ka "sab True" matrix; `np.triu` = sirf upar ka hissa rakhta hai.
- `mask=mask` → Jahan `mask` True ho, woh cell **chhupa** diya jata hai. Correlation matrix symmetric hota hai, is liye aadha kafi hai.
- `vmin=-1, vmax=1` → Color scale ko -1 se +1 tak fix kiya taake rang ka matlab hamesha same rahe.
- `linewidths=0.5` → Cells ke beech patli line.
- `square=True` → Har cell **chowkor** shakal mein.
- `select_dtypes(include="number")` → Sirf numeric columns chunta hai.
- `.drop(columns="student_id")` → ID column hataya.

| Parameter | Matlab | Required? |
|---|---|---|
| `data` (pehla argument) | 2D table/matrix | Zaroori |
| `annot` | Cell mein numbers | Optional |
| `cmap` | Rangon ka set | Optional |
| `fmt` | Numbers ka format | Optional (annot ke saath) |
| `vmin`, `vmax` | Color scale ki hadein | Optional |
| `linewidths` | Cells ke beech line | Optional |
| `mask` | Kuch cells chhupana | Optional |

### 9. Output Ki Explanation
Hamare synthetic data mein (approximately):
- `study_hours` aur `final_marks` ka correlation **≈ 0.67** → moderate-to-strong positive.
- `attendance` aur `final_marks` ka correlation **≈ 0.59** → moderate positive.
- `study_hours` aur `attendance` ka correlation **≈ 0.63** → aapas mein bhi related hain.
- `math_marks` aur `final_marks` ka correlation **≈ 0.98** → bohat strong. **Yeh isliye hai kyun ke `final_marks` khud math, science, english se bana hai** (hum ne formula se banaya). Is ko "interesting discovery" na samjhein; yeh data ke banne ka natija hai.
- **Nateeja:** Jo students zyada parhte hain, un ki attendance aur marks bhi aam tor par zyada hain. Lekin **yeh wajah (cause) nahi, sirf rishta hai.**

### 10. Common Mistakes
| Ghalti | Sahi |
|---|---|
| Poora `df.corr()` chalana jab text columns hon | `select_dtypes("number")` ya `numeric_only=True` |
| `student_id` ko correlation mein shamil karna | ID drop karein |
| Strong correlation ko causation samajhna | Sirf "related" kahein |
| `fmt=".2f"` ke bagair `annot=True` mein bohat lambe decimals | `fmt` set karein |
| Bohat zyada columns (50+) ki heatmap | Important columns chunein |

### 11. Real Project Use
- Machine learning se pehle **multicollinearity** dekhna (do features bohat zyada related hon to model confuse ho sakta hai).
- Marketing: kaun si cheezein sales se related hain.
- Finance: stocks ka aapas mein rishta.

### 12. Practice Task
1. Sirf `math_marks`, `science_marks`, `english_marks` ki heatmap.
2. `cmap="viridis"` aur `"Blues"` try karein.
3. Heatmap mein se woh pair dhoondhein jis ka correlation sab se kam ho.

### 13. Quiz
1. Correlation ki range? → **-1 se +1.**
2. Diagonal par kya hota hai? → **1.00**
3. `annot=True` kya karta hai? → **Cells mein numbers dikhata hai.**
4. `mask` kyun use karte hain? → **Cells chhupane ke liye (jaise duplicate upar ka triangle).**
5. Strong correlation = cause? → **Nahi.**

---

## Chapter 8: Pairplot — `sns.pairplot()`

### 1. Pairplot Kya Hai?
**Pairplot** ek **graphs ka grid** hai jo **kai numerical columns ke har jore (pair)** ko aapas mein dikhata hai. Ek hi command se darjanon graphs.

### 2. Kyun Use Hota Hai?
Ek hi nazar mein dekhne ke liye ke **kaun se columns aapas mein related hain** aur har column ki **distribution** kaisi hai.

### 3. Kab Use Hota Hai?
EDA ke **shuru mein**, jab data naya ho aur aap ko andaza lagana ho ke kahan dekhna chahiye.

### 4. Real-Life Example
Ek doctor ek hi report mein blood pressure, sugar, weight aur age sab ka aapas mein rishta dekh leta hai.

### 5. Graph Kaise Read Karein?
Agar 4 columns hon (`study_hours`, `attendance`, `math_marks`, `final_marks`), to 4×4 grid banega:
- **Diagonal par:** Har akele column ka **histogram** (ya KDE). Yeh bataata hai ke us column ki distribution kaisi hai.
- **Diagonal se bahar:** Do columns ka **scatter plot**. Row ka variable y-axis par aur column ka variable x-axis par.
- **`corner=True`:** Sirf neeche ka triangle dikhata hai (kyun ke upar wala neeche wale ka ulta/mirror hota hai).
- **Colors (`hue`):** Pass aur Fail ke dots alag rang mein.

### 6. Required Data
**Kai numerical columns.** Optional: ek categorical column `hue` ke liye.

### 7. Complete Code

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_theme(style="whitegrid")
df = pd.read_csv("student_performance.csv")

# Graph 1: Sirf zaroori columns, hue ke saath
g = sns.pairplot(
    df,
    vars=["study_hours", "attendance", "math_marks", "final_marks"],
    hue="passed",
    diag_kind="hist",
    corner=True,
)
g.figure.suptitle("Pairplot of Student Performance", y=1.02)
plt.show()

# Graph 2: Sirf kuch combinations (x_vars aur y_vars)
sns.pairplot(
    df,
    x_vars=["study_hours", "attendance"],
    y_vars=["final_marks"],
    height=4,
    kind="reg",
)
plt.show()
```

### 8. Line-by-Line Explanation
- `sns.pairplot(df, ...)` → Pehla argument poora DataFrame.
- `vars=[...]` → **Sirf in 4 columns** ka grid banao. Agar `vars` na dein to **tamam numerical columns** (student_id tak) shamil ho jayenge aur grid bohat bara aur ulajh hua banega.
- `hue="passed"` → Pass aur Fail ko alag colors.
- `diag_kind="hist"` → Diagonal par histogram. Options: `"hist"`, `"kde"`, `None`.
- `corner=True` → Sirf neeche ka triangle (aadha grid), jagah aur waqt ki bachat.
- `g = ...` → Pairplot ek `PairGrid` object wapas karta hai. Us se `g.figure` (poora figure) mil jata hai.
- `g.figure.suptitle("...", y=1.02)` → Poore grid ka ek **bara title**. `y=1.02` title ko thora upar le jata hai taake overlap na ho. (Purane Seaborn mein `g.fig` hota tha; naye mein `g.figure`.)
- `x_vars`, `y_vars` → Grid mein **kaun se columns x par aur kaun se y par** hon. Is se hum sirf wahi graphs banate hain jinki zaroorat ho.
- `height=4` → Har chhote graph ki height 4 inch.
- `kind="reg"` → Har scatter par **regression line** bhi lagao. Options: `"scatter"` (default), `"kde"`, `"hist"`, `"reg"`.

| Parameter | Matlab | Required? |
|---|---|---|
| `data` | DataFrame | Zaroori |
| `vars` | Kaun se columns | Optional (default: sab numeric) |
| `x_vars`, `y_vars` | Alag x aur y columns | Optional |
| `hue` | Color group | Optional |
| `diag_kind` | Diagonal graph ki qism | Optional |
| `corner` | Aadha grid | Optional |
| `kind` | Off-diagonal graph ki qism | Optional |
| `height` | Har subplot ka size | Optional |

### 9. Output Ki Explanation
- `study_hours` vs `final_marks` ka scatter **upar ki taraf** jata nazar aata hai → positive relationship.
- `math_marks` vs `final_marks` ke dots **lagbhag seedhi line** mein hain (kyun ke `final_marks` math se bana hai).
- **Fail** (marks 40 se kam) ke dots hamesha **neeche** hain, kyun ke fail ka tareeqa `final_marks` se tay hua. Isay "pattern" na samjhein, yeh **definition ka asar** hai.
- Diagonal ke histograms se har column ki shape dikhti hai.

### Performance Ka Masla
- 4 columns = 16 plots (corner se 10). **20 columns = 400 plots.**
- 100,000 rows × bohat saare columns = **bohat slow**, computer hang ho sakta hai.
- **Hal:**
  1. Sirf **important columns** chunein (`vars`).
  2. Bare data ka **sample** lein: `df.sample(1000, random_state=42)`.
  3. `corner=True` lagayein.

> **Sikhne ki baat:** Pairplot ko **andha-dhundh poore dataset** par na chalayein. Pehle sochein: kaun se 4-6 columns business sawal se related hain?

### 10. Common Mistakes
| Ghalti | Sahi |
|---|---|
| Poora dataset de dena (ID tak) | `vars=[...]` se chunein |
| Bohat zyada columns | 4-6 columns se shuru karein |
| `hue` par bohat zyada categories | 2-4 categories kafi |
| `g.fig` purane syntax | `g.figure` naye Seaborn mein |
| Pairplot ko final report ka asli graph samajhna | Yeh **exploration** tool hai |

### 11. Real Project Use
- Naye dataset ka **pehla jaiza**.
- Feature selection ke liye pehla andaza.
- Clusters ya groups dhoondhna (`hue` se).

### 12. Practice Task
1. `hue="gender"` ke saath pairplot banayein.
2. `diag_kind="kde"` try karein.
3. `df.sample(20)` par pairplot chalayein aur farq dekhein.

### 13. Quiz
1. Pairplot kya hai? → **Kai columns ke pairs ka grid.**
2. Diagonal par kya hota hai? → **Har akele column ka histogram/KDE.**
3. `corner=True` ka faida? → **Sirf neeche ka triangle dikhata hai.**
4. Bare data par pairplot ka masla? → **Slow ho jata hai.**

---

## Chapter 9: Regression Plot — `sns.regplot()`

### 1. Regression Plot Kya Hai?
**Regression plot** scatter plot ke upar ek **fitted line** (best-fit line) lagata hai jo dots ke **general rujhan (trend)** ko dikhati hai.

### 2. Kyun Use Hota Hai?
Do numerical variables ka **trend** aur **line ki slope** (dhalan) dekhne ke liye.

### 3. Kab Use Hota Hai?
Jab scatter plot mein seedhi line jaisa rishta nazar aaye aur aap uski direction aur strength dekhna chahein.

### 4. Real-Life Example
*"Har extra ghante ki parhai se marks lagbhag kitne barhte hain?"* Line ki slope is sawal ka andaza deti hai.

### 5. Graph Kaise Read Karein?
- **Dots** = asal data.
- **Seedhi line** = regression line (dots ke aas paas se guzarti hui best-fit line).
- **Shaded band** = **Confidence interval** (line ki uncertainty).
- **Line upar jaye** = positive trend, **neeche jaye** = negative trend.
- **Dots line ke jitne qareeb** = rishta utna mazboot.
- **Dots line se door door** = rishta kamzor.

### 6. Required Data
Do numerical columns.

### 7. Complete Code

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_theme(style="whitegrid")
df = pd.read_csv("student_performance.csv")

# ---- Graph 1: Basic regplot ----
plt.figure(figsize=(7, 5))
sns.regplot(data=df, x="study_hours", y="final_marks")
plt.title("Study Hours vs Final Marks (with Regression Line)")
plt.xlabel("Study Hours (per day)")
plt.ylabel("Final Marks")
plt.tight_layout()
plt.show()

# ---- Graph 2: Customization ----
plt.figure(figsize=(7, 5))
sns.regplot(
    data=df,
    x="attendance",
    y="final_marks",
    ci=95,
    scatter_kws={"alpha": 0.6, "s": 60},
    line_kws={"color": "red", "linewidth": 2},
)
plt.title("Attendance vs Final Marks")
plt.xlabel("Attendance (%)")
plt.ylabel("Final Marks")
plt.tight_layout()
plt.show()

# ---- Graph 3: Curve (order=2) ----
plt.figure(figsize=(7, 5))
sns.regplot(data=df, x="study_hours", y="final_marks", order=2)
plt.title("Polynomial Fit (order=2)")
plt.tight_layout()
plt.show()

# ---- Slope ka andaza (NumPy se) ----
import numpy as np
slope, intercept = np.polyfit(df["study_hours"], df["final_marks"], 1)
print("Slope:", round(slope, 2), "| Intercept:", round(intercept, 2))
```

### 8. Line-by-Line Explanation
- `sns.regplot(data=df, x=..., y=...)` → Scatter + regression line.
- `ci=95` → Confidence interval 95%. `ci=None` = shaded band nahi.
- `scatter_kws={"alpha": 0.6, "s": 60}` → **Scatter dots** ki settings: transparency 0.6 aur size 60. (`kws` = keyword arguments.)
- `line_kws={"color": "red", "linewidth": 2}` → **Regression line** ki settings: laal rang, moti 2.
- `order=2` → Seedhi line ke bajaye **curve** (degree 2 polynomial). Bohat zyada order (jaise 8) **overfitting** karta hai.
- `np.polyfit(x, y, 1)` → Degree-1 (seedhi line) fit karke **slope** aur **intercept** nikalta hai.
- `slope` = x mein 1 unit izafay par y mein kitna izafa (aam tor par).
- `intercept` = x = 0 par line ki y value.

**Aur parameters (optional, extra libraries chahiye):**

| Parameter | Matlab | Note |
|---|---|---|
| `robust=True` | Outliers ka asar kam karta hai | **`statsmodels`** install hona chahiye: `pip install statsmodels` |
| `lowess=True` | Smooth, flexible curve (seedhi line nahi) | **`statsmodels`** chahiye |
| `scatter=False` | Dots chhupa kar sirf line | Optional |
| `logistic=True` | Logistic regression (0/1 outcome ke liye) | `statsmodels` chahiye |

```python
# statsmodels install karne ke baad:
sns.regplot(data=df, x="study_hours", y="final_marks", robust=True)
sns.regplot(data=df, x="study_hours", y="final_marks", lowess=True)
```

### regplot vs lmplot

| `regplot` | `lmplot` |
|---|---|
| **Axes-level** function (ek `ax` par chalta hai) | **Figure-level** function (apna figure banata hai) |
| `plt.figure(figsize=...)` se size set | `height` aur `aspect` se size set |
| `hue` nahi (ek hi regression) | **`hue`, `col`, `row`** se alag alag regression lines |
| Subplots ke andar rakh sakte hain | Subplots ke andar nahi rakh sakte |

```python
# lmplot: Male aur Female ki alag alag lines
sns.lmplot(data=df, x="study_hours", y="final_marks", hue="gender", height=5, aspect=1.3)
plt.show()
```
- `hue="gender"` → Male aur Female ki **alag line**.
- `height=5` aur `aspect=1.3` → Graph ki height 5 inch aur chorai = 5×1.3.

### 9. Output Ki Explanation
- `study_hours` vs `final_marks` ki line **upar ja rahi hai** (positive slope).
- NumPy ka `polyfit` is data mein slope lagbhag **5.5 marks per extra study hour** deta hai (approximately); yani **is sample mein** har 1 extra ghante ke saath marks ka average ~5.5 ke qareeb barhta nazar aata hai. **Yeh guarantee nahi.**
- Kuch dots line se **bohat door** hain (Hamza ka 1 ghanta par ~88 marks, Maryam ka 8 ghante par ~31 marks). Yeh line ko thora kheench sakte hain.

### Regression Line Prediction Ki Guarantee Kyun Nahi?
1. **Sample chhota** hai (sirf 40 students).
2. **Aur factors** (talent, pichli taleem, sehat) data mein nahi hain.
3. Line sirf **average trend** hai. Har individual student us par nahi hota.
4. Data ki range se **bahar** (jaise 15 ghante study) line par bharosa nahi karna.

### Linear Relationship Kab Suitable Hai?
Jab dots ek seedhi patti jaisi shakal mein hon. Agar dots **curve (U-shape ya S-shape)** ban rahe hon, to seedhi line theek nahi.

### Overfitting Ka Basic Introduction
**Overfitting** = Model ya line data ko **itna zyada yaad** kar leti hai ke **naye data par fail** ho jati hai.
**Misaal:** Ek student ne pichle 5 saal ke paper ke **sirf jawab ratt** liye. Ab sawal thora alag aaya to fail. `order=10` jaisi bohat tedhi line bhi aisi hi hai.

> **Zaroori:** `regplot` **EDA** (data samajhne) ke liye hai. Agar aap ko **asal prediction model** banana hai, to alag se **train/test split**, **model training** aur **evaluation** (jaise scikit-learn se) karna hoga.

### 10. Common Mistakes
| Ghalti | Sahi |
|---|---|
| Line ko "pakka prediction" samajhna | Line sirf trend dikhati hai |
| `lowess=True`/`robust=True` par `statsmodels` na hona | `pip install statsmodels` |
| Bohat zyada `order` | 1 ya 2 se shuru karein |
| Categorical column ko `x`/`y` banana | Numerical columns |
| Outliers ko nazar andaz karna | Outliers line ko mod sakte hain |

### 11. Real Project Use
- House area vs price ka trend.
- Marketing spend vs sales.
- Kisi model ka pehla andaza (baseline).

### 12. Practice Task
1. `attendance` vs `math_marks` ka regplot.
2. `ci=None` lagayein aur farq dekhein.
3. `lmplot` mein `hue="passed"` ya `col="class"` lagayein.

### 13. Quiz
1. Regression line kya hai? → **Dots ko behtareen tareeqe se darmiyan se guzarne wali line.**
2. `ci=95` kya hai? → **95% confidence band.**
3. `regplot` aur `lmplot` mein farq? → **lmplot figure-level hai aur hue/col/row support karta hai.**
4. Overfitting kya hai? → **Data ko bohat zyada ratt lena.**
5. Kya regplot prediction ki guarantee deta hai? → **Nahi.**

---

## Chapter 10: Violin Plot — `sns.violinplot()`

### 1. Violin Plot Kya Hai?
**Violin plot** box plot jaisa hota hai, lekin us mein **distribution ki poori shakal** (KDE) bhi nazar aati hai. Is ki shakal **violin (saaz)** jaisi hoti hai.

### 2. Kyun Use Hota Hai?
Yeh dekhne ke liye ke **data kahan zyada ghana (dense) hai** aur kahan kam, har group mein.

### 3. Kab Use Hota Hai?
Jab **groups ki distribution ki shakal** ka muqabla karna ho (kya ek group ke do "peaks" hain?).

### 4. Real-Life Example
*"Class 8, 9 aur 10 ke marks ki distribution mein kya farq hai?"*

### 5. Graph Kaise Read Karein?
- **Violin ki width:** Us value ke qareeb **kitne zyada students**. Jahan **chora**, wahan zyada students; jahan **patla**, wahan kam.
- **Andar ka mini box plot** (default): median aur quartiles.
- **KDE (Kernel Density Estimate):** Data ki **smooth density curve**. Histogram ka naram version. Isi se violin ki bahar ki shakal banti hai.
- **Do violins ka alag shape** = distributions alag.

### Box Plot vs Violin Plot

| Box Plot | Violin Plot |
|---|---|
| Sada, 5 numbers | Poori shakal + andar box |
| Parhna asaan | Thora mushkil, beginners ke liye |
| Chhote data par behtar | Kam data par KDE gumrah kar sakti hai |
| Outliers alag dots | Outliers aksar violin ki dum mein |

### 6. Required Data
Ek numerical column aur (optional) ek categorical column.

### 7. Complete Code

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_theme(style="whitegrid")
df = pd.read_csv("student_performance.csv")

# ---- Graph 1: Class-wise violin ----
plt.figure(figsize=(8, 6))
sns.violinplot(
    data=df,
    x="class",
    y="final_marks",
    order=["Class 8", "Class 9", "Class 10"],
    hue="class",
    palette="Set2",
    legend=False,
    inner="box",
    cut=0,
    density_norm="width",
)
plt.title("Final Marks Distribution by Class")
plt.xlabel("Class")
plt.ylabel("Final Marks")
plt.tight_layout()
plt.show()

# ---- Graph 2: Split violin (Male vs Female) ----
plt.figure(figsize=(8, 6))
sns.violinplot(
    data=df,
    x="class",
    y="final_marks",
    hue="gender",
    split=True,
    order=["Class 8", "Class 9", "Class 10"],
    inner="quart",
    cut=0,
)
plt.title("Final Marks by Class: Male vs Female")
plt.xlabel("Class")
plt.ylabel("Final Marks")
plt.legend(title="Gender")
plt.tight_layout()
plt.show()
```

### 8. Line-by-Line Explanation
- `sns.violinplot(data=df, x="class", y="final_marks")` → Har class ke liye ek violin.
- `order=[...]` → Violins ki tarteeb.
- `hue="class", palette="Set2", legend=False` → Har violin ko alag color.
- `inner="box"` → Violin ke andar kya dikhana hai. Options: `"box"`, `"quart"` (quartile lines), `"point"`, `"stick"`, `None`.
- `cut=0` → Violin ko **data ki min/max par hi kaat do**. Default `cut=2` hai jis mein violin data ki range se **bahar** tak phail jati hai (kabhi kabhi 100 se zyada marks dikhate hain jo nahi ho sakte).
- `density_norm="width"` → Har violin ki **maximum chorai barabar**. Options: `"area"` (default; sab violins ka area barabar), `"count"` (zyada data wala violin chora), `"width"`. (**Purana naam `scale=`** tha; naye Seaborn mein `density_norm`.)
- `hue="gender"` + `split=True` → Har violin **aadha Male, aadha Female**. `split=True` **sirf tab** kaam karta hai jab `hue` mein **exactly 2** categories hon.
- `inner="quart"` → Median aur quartiles ki dotted lines.

| Parameter | Matlab | Required? |
|---|---|---|
| `data`, `x`, `y` | Data aur columns | Kam az kam ek numerical axis |
| `hue` | Sub-groups | Optional |
| `split` | Do groups ek violin mein | Optional (hue ke saath, 2 categories) |
| `inner` | Andar ka nishan | Optional |
| `cut` | Violin ki dum kitni lambi | Optional |
| `density_norm` | Violins ki size ka normalization | Optional |
| `order` | Tarteeb | Optional |

### 9. Output Ki Explanation
- **Class 10** ka median (~66.9) teeno classes mein sab se zyada hai, is liye us ka violin dusron ke muqable mein upar ki taraf zyada chora nazar aata hai.
- **Class 9** ka phailao sab se kam hai (standard deviation ~14.7, jabke Class 8 ~17.7 aur Class 10 ~18.2). **Class 8** mein marks ki range sab se bari hai (~29 se ~88).
- Split violin se Male aur Female ki distribution ek hi violin mein muqabla hoti hai.
- **Yaad rakhein:** Har class mein sirf 11 se 17 students hain. Itne kam data par violin ki **smooth shakal par zyada bharosa nahi** karna chahiye.

### Violin vs Box: Kab Konsa?
- **Violin:** Jab data zyada ho (kam az kam 30-50 per group) aur distribution ki shakal (do peaks?) dikhani ho.
- **Box plot:** Jab data kam ho, ya audience beginner ho, ya sirf median/outlier chahiye.

### 10. Common Mistakes
| Ghalti | Sahi |
|---|---|
| Violin par chhote data par zyada bharosa | Kam data par box plot behtar |
| `split=True` ke saath 3 categories ka `hue` | Sirf 2 categories |
| `scale=` purana parameter | `density_norm=` naya |
| `cut=0` bhool jana aur "100 se zyada marks" dikhna | `cut=0` lagayein |
| Beginners ko samjhaye bagair dikhana | Pehle box plot sikhayein |

### 11. Real Project Use
- Customer spending ki distribution segment-wise.
- A/B test mein groups ki shakal ka muqabla.
- Do hospitals ke waiting time distributions.

### 12. Practice Task
1. `city` ke mutabiq violin plot banayein.
2. `inner="point"` aur `inner="stick"` try karein.
3. `attendance` ke liye class-wise violin banayein.

### 13. Quiz
1. Violin ki width kya batati hai? → **Us jagah data ki density.**
2. KDE kya hai? → **Smooth density curve.**
3. `split=True` kab chalta hai? → **hue mein sirf 2 categories ho to.**
4. Chhote data par kaun sa plot behtar? → **Aksar box plot.**

---

## Chapter 11: Subplots — `plt.subplots()`

### 1. Subplot Kya Hai?
**Subplot** = ek hi **figure (kaghaz)** par **kai chhote graphs** lagana.

### 2. Kyun Use Hota Hai?
- Ek nazar mein **kai graphs ka muqabla**.
- **Dashboard** ya report ka ek page banana.
- Presentation mein jagah ki bachat.

### 3. Kab Use Hota Hai?
Jab aap ke paas ek hi dataset ke baare mein kai alag graphs hon aur sab ko saath dikhana ho.

### 4. Real-Life Example
Report card ke ek page par: marks ki distribution, study hours ka rishta, aur class-wise comparison, **sab ek page par.**

### 5. Zaroori Terms
- **Figure (`fig`)** = Poora kaghaz/canvas jis par sab kuch banta hai.
- **Axes (`ax`)** = Figure ke andar **ek chhota graph** ka area (x-axis, y-axis aur data samet). **Ek figure mein kai axes ho sakte hain.**
- **`nrows`** = Kitni rows (qataar).
- **`ncols`** = Kitne columns.
- **`axes`** = Un tamam axes ka array.
- **`figsize`** = Poore figure ka size (chorai, lambai).
- **`tight_layout()`** = Graphs ko aapas mein overlap hone se bachata hai.

**`plt` aur `ax` mein farq:**
| `plt.title(...)` | `ax.set_title(...)` |
|---|---|
| "Abhi jo graph active hai us par lagao" | "Is **khaas** axes par lagao" |
| Ek graph ke liye theek | Kai subplots ke liye **zaroori** |
| Pyplot interface | Object-oriented interface |

**Axes ko kaise address karein?**
- **1 row, 3 columns:** `axes` ek **1D array** hai → `axes[0]`, `axes[1]`, `axes[2]`.
- **2 rows, 2 columns:** `axes` ek **2D array** hai → `axes[0, 0]` (upar-left), `axes[0, 1]` (upar-right), `axes[1, 0]` (neeche-left), `axes[1, 1]` (neeche-right).

### 6. Required Data
Jo graphs banane hain unka data (hum student data aur monthly data dono use karenge).

### 7. Complete Code

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_theme(style="whitegrid")
df = pd.read_csv("student_performance.csv")
monthly = pd.read_csv("monthly_performance.csv")

# 2 rows x 2 columns ka figure
fig, axes = plt.subplots(nrows=2, ncols=2, figsize=(12, 9))

# Upar-left: Line plot (monthly data)
sns.lineplot(data=monthly, x="month", y="avg_marks", hue="class",
             marker="o", errorbar=None, ax=axes[0, 0])
axes[0, 0].set_title("Monthly Average Marks")
axes[0, 0].set_xlabel("Month")
axes[0, 0].set_ylabel("Average Marks")

# Upar-right: Histogram
sns.histplot(data=df, x="final_marks", bins=8, kde=True, ax=axes[0, 1])
axes[0, 1].set_title("Distribution of Final Marks")
axes[0, 1].set_xlabel("Final Marks")
axes[0, 1].set_ylabel("Number of Students")

# Neeche-left: Scatter plot
sns.scatterplot(data=df, x="study_hours", y="final_marks", hue="passed", ax=axes[1, 0])
axes[1, 0].set_title("Study Hours vs Final Marks")
axes[1, 0].set_xlabel("Study Hours")
axes[1, 0].set_ylabel("Final Marks")

# Neeche-right: Box plot
sns.boxplot(data=df, x="class", y="final_marks",
            order=["Class 8", "Class 9", "Class 10"],
            hue="class", palette="Set2", legend=False, ax=axes[1, 1])
axes[1, 1].set_title("Final Marks by Class")
axes[1, 1].set_xlabel("Class")
axes[1, 1].set_ylabel("Final Marks")

fig.suptitle("Student Performance Dashboard (Synthetic Data)", fontsize=16)
fig.tight_layout()
plt.show()
```

### 8. Line-by-Line Explanation
- `fig, axes = plt.subplots(nrows=2, ncols=2, figsize=(12, 9))` → 2×2 ka figure. `fig` poora kaghaz, `axes` chaar chhote graphs ka 2D array.
- `ax=axes[0, 0]` → Seaborn ko batata hai: **yeh graph is khaas jagah par banao.** Har Seaborn axes-level function (lineplot, histplot, scatterplot, boxplot, barplot, countplot, heatmap, violinplot, regplot) `ax=` leta hai.
- `axes[0, 0].set_title(...)` → Us **specific** graph ka title. Subplots mein `plt.title` ki jagah `set_title` use hota hai.
- `.set_xlabel()`, `.set_ylabel()` → Us graph ke axis labels.
- `fig.suptitle("...", fontsize=16)` → **Poore figure** ka mukhya title.
- `fig.tight_layout()` → Overlap rokta hai.
- `plt.show()` → Dikhata hai.

> **Note:** `pairplot` aur `lmplot` **figure-level** functions hain; yeh `ax=` nahi lete aur subplots ke andar nahi rakhe ja sakte. Inke liye alag se figure banta hai.

**Chhota misaal: 1 row, 3 columns**

```python
fig, axes = plt.subplots(1, 3, figsize=(15, 4))
sns.histplot(df["math_marks"], ax=axes[0])
sns.histplot(df["science_marks"], ax=axes[1])
sns.histplot(df["english_marks"], ax=axes[2])
axes[0].set_title("Math")
axes[1].set_title("Science")
axes[2].set_title("English")
fig.tight_layout()
plt.show()
```
- `plt.subplots(1, 3, ...)` → 1 row, 3 columns; `axes` 1D hai → `axes[0]`, `axes[1]`, `axes[2]`.
- `sns.histplot(df["math_marks"], ax=axes[0])` → Ek Series seedha bhi de sakte hain.

### 9. Output Ki Explanation
Ek figure mein 4 graphs hain:
1. **Line plot:** Teeno classes ki performance mahine ke saath behtar.
2. **Histogram:** Sab se zyada students 50-70 final marks ki range mein hain.
3. **Scatter:** Zyada study hours par zyada marks (aam tor par), Fail dots neeche.
4. **Box plot:** Class-wise median aur phailao.

Is tarah ek **mini dashboard** ban jata hai.

### 10. Common Mistakes
| Ghalti | Sahi |
|---|---|
| Subplots mein `plt.title()` | `axes[i].set_title()` |
| 1D aur 2D `axes` ka index confuse karna | 1 row/col = `axes[i]`, 2D = `axes[r, c]` |
| `ax=` dena bhool jana | Graph aakhri axes par ya alag figure mein banega |
| `tight_layout()` bhool jana | Labels overlap |
| `pairplot` ko `ax=` ke saath chalana | Figure-level hai; alag banayein |

### 11. Real Project Use
- Management dashboard.
- Research paper ka multi-panel figure.
- Model ke training/validation curves ke saath-saath.

### 12. Practice Task
1. 1×3 subplots: math, science, english ke box plots.
2. 2×2 grid: bar plot, count plot, histogram, scatter plot.
3. `plt.subplots(2, 1, sharex=True)` try karein.

### 13. Quiz
1. `fig` aur `ax` mein farq? → **fig poora kaghaz, ax ek chhota graph.**
2. `plt.subplots(2, 3)` kitne graphs? → **6.**
3. 2D axes mein upar-right ka index? → **`axes[0, 1]`**
4. Subplot mein title kaise? → **`axes[i].set_title("...")`**

---
# PART 4: Har Graph Ke Important Parameters Ki Complete Guide

> **Version note (bohat zaroori):** Har parameter har version mein available nahi hota. Is course ka code **Seaborn 0.13+** aur **Matplotlib 3.8+** ke liye hai. Apna version check karein: `print(sns.__version__)`.
>
> **Required vs Optional:** Neeche har table mein "Required?" column hai. Aam tor par `data`, `x`/`y` ke ilawa **koi bhi parameter lazmi nahi**. `hue`, `color`, `bins`, `palette` jaise parameters **optional** hain; unke bagair bhi graph ban jata hai.

## 4.1 Purane Parameters Se Bachein (Deprecated / Changed)

| Purana (avoid karein) | Naya (use karein) | Kis liye |
|---|---|---|
| `ci=95` (barplot/lineplot) | `errorbar=("ci", 95)` | Error bars (Seaborn 0.12+). `regplot` mein `ci=` ab bhi chalta hai |
| `scale="width"` (violinplot) | `density_norm="width"` | Violin normalization |
| `bw="scott"` (violinplot/kdeplot) | `bw_method=` / `bw_adjust=` | KDE smoothness |
| `sns.distplot()` | `sns.histplot()` ya `sns.displot()` | Distribution |
| `palette=...` bina `hue` ke | `hue="col"`, `palette=...`, `legend=False` | Colors |
| `g.fig` (PairGrid) | `g.figure` | Figure access |
| `sns.set()` | `sns.set_theme()` | Default theme |

## 4.2 `lineplot` Parameters

| Parameter | Simple Meaning | Kab Use Karein | Chhota Example | Na dein to? | Required? |
|---|---|---|---|---|---|
| `data` | DataFrame | Column names use karne hon | `data=monthly` | Column names kaam nahi karenge | Practically yes |
| `x` | X-axis column | Hamesha | `x="month"` | Graph nahi banta | Yes |
| `y` | Y-axis column | Hamesha | `y="avg_marks"` | Graph nahi banta | Yes |
| `hue` | Rang se group | Groups compare karne hon | `hue="class"` | Ek hi line | No |
| `style` | Line style se group | B/W print ya extra group | `style="class"` | Sab lines ek style | No |
| `marker` | Har point ka nishan | Points highlight karne hon | `marker="o"` | Sirf line, markers nahi | No |
| `errorbar` | Uncertainty band | Ek x par kai values hon | `errorbar=None` | Default: 95% CI band | No |
| `estimator` | Ek x ki values ka summary | Average ke bajaye median | `estimator="median"` | Mean | No |
| `linewidth` | Line ki motai | Zyada nazar aane ke liye | `linewidth=3` | Default motai | No |

## 4.3 `barplot` Parameters

| Parameter | Simple Meaning | Kab Use Karein | Example | Na dein to? | Required? |
|---|---|---|---|---|---|
| `x`, `y` | Category aur numeric | Hamesha | `x="class", y="final_marks"` | Graph nahi | Yes |
| `data` | DataFrame | Column names | `data=df` | Names kaam nahi | Practically yes |
| `hue` | Sub-category (rang) | Groups ke andar groups | `hue="gender"` | Ek rang | No |
| `order` | Bars ki tarteeb | Tarteeb fix karni ho | `order=["Class 8","Class 9","Class 10"]` | Data ki pehli appearance wali tarteeb | No |
| `estimator` | Kaun si summary | Sum/median chahiye | `estimator="sum"` | `mean` | No |
| `errorbar` | Error line | Uncertainty dikhani ho | `errorbar=("sd")` ya `None` | 95% CI | No |
| `palette` | Colors | Khoobsurti | `palette="Set2"` (hue ke saath) | Default colors | No |
| `orient` | Bars ka rukh | `"h"` horizontal | `orient="h"` | Auto | No |

## 4.4 `scatterplot` Parameters

| Parameter | Meaning | Kab Use Karein | Example | Na dein to? | Required? |
|---|---|---|---|---|---|
| `x`, `y` | Do numeric columns | Hamesha | `x="study_hours", y="final_marks"` | Graph nahi | Yes |
| `hue` | Rang (category ya number) | Groups dekhne hon | `hue="passed"` | Ek rang | No |
| `size` | Dot ka size column se | Teesra numeric variable | `size="attendance"` | Sab dots barabar | No |
| `style` | Dot ki shape | Category ko shape se | `style="gender"` | Ek shape | No |
| `alpha` | Transparency 0-1 | Overlapping dots | `alpha=0.6` | Thos dots | No |
| `s` | Fixed size | Sab dots ka size | `s=80` | Default | No |

## 4.5 `histplot` Parameters

| Parameter | Meaning | Kab Use Karein | Example | Na dein to? | Required? |
|---|---|---|---|---|---|
| `x` (ya `y`) | Numeric column | Hamesha | `x="final_marks"` | Graph nahi | Yes |
| `bins` | Dabbon ki tadaad | Detail control | `bins=10` | Seaborn khud chunta hai | No |
| `binwidth` | Dabbe ki chorai | Fixed range chahiye | `binwidth=10` | Auto | No |
| `kde` | Smooth curve | Shape dekhni ho | `kde=True` | Curve nahi | No |
| `stat` | Y-axis ka matlab | Percent/density | `stat="percent"` | `count` | No |
| `element` | Bars ya outline | Overlay graphs | `element="step"` | `bars` | No |
| `hue` | Group | Do distributions compare | `hue="gender"` | Ek distribution | No |
| `multiple` | Hue groups kaise rakhein | layer/stack/dodge | `multiple="stack"` | `layer` | No |

## 4.6 `boxplot` Parameters

| Parameter | Meaning | Kab Use Karein | Example | Na dein to? | Required? |
|---|---|---|---|---|---|
| `x`, `y` | Numeric (+ category) | Hamesha ek numeric | `x="class", y="final_marks"` | Graph nahi | Yes (numeric) |
| `hue` | Sub-group | Do groups per category | `hue="gender"` | Ek box per category | No |
| `order` | Boxes ki tarteeb | Tarteeb fix | `order=[...]` | Default | No |
| `showfliers` | Outlier dots dikhana | Dots nahi chahiye | `showfliers=False` | `True` | No |
| `whis` | Whisker ki lambai (IQR ka multiple) | Rule badalna ho | `whis=1.5` | `1.5` | No |
| `width` | Box ki chorai | Look | `width=0.5` | Default | No |

## 4.7 `countplot` Parameters

| Parameter | Meaning | Kab Use Karein | Example | Na dein to? | Required? |
|---|---|---|---|---|---|
| `x` **ya** `y` | Categorical column | Hamesha (ek hi) | `x="passed"` | Graph nahi | Yes |
| `hue` | Sub-group | Do categories ka cross | `hue="gender"` | Ek rang | No |
| `order` | Tarteeb | Fix tarteeb | `order=["Pass","Fail"]` | Appearance order | No |
| `stat` | count/percent | Percentage chahiye | `stat="percent"` | `count` | No |
| `palette` | Colors | Look | `palette="pastel"` | Default | No |

## 4.8 `heatmap` Parameters

| Parameter | Meaning | Kab Use Karein | Example | Na dein to? | Required? |
|---|---|---|---|---|---|
| `data` (pehla) | 2D matrix | Hamesha | `sns.heatmap(corr)` | Graph nahi | Yes |
| `annot` | Cell mein number | Exact values dikhani hon | `annot=True` | Sirf rang | No |
| `fmt` | Number ka format | `annot` ke saath | `fmt=".2f"` | Default format | No |
| `cmap` | Color map | Look/meaning | `cmap="coolwarm"` | Default colormap | No |
| `vmin`, `vmax` | Color ki hadein | Correlation (-1..1) | `vmin=-1, vmax=1` | Data ki min/max | No |
| `linewidths` | Cell border | Saaf look | `linewidths=0.5` | Koi line nahi | No |
| `mask` | Cells chhupana | Upar ka triangle | `mask=mask` | Sab cells | No |
| `square` | Chowkor cells | Neat look | `square=True` | Rectangular | No |

## 4.9 `pairplot` Parameters

| Parameter | Meaning | Kab Use Karein | Example | Na dein to? | Required? |
|---|---|---|---|---|---|
| `data` (pehla) | DataFrame | Hamesha | `sns.pairplot(df)` | Graph nahi | Yes |
| `vars` | Kaun se columns | Zaroori columns | `vars=["study_hours","final_marks"]` | Sab numeric columns | No |
| `x_vars`, `y_vars` | Alag x aur y list | Rectangular grid | `x_vars=[...], y_vars=[...]` | Square grid | No |
| `hue` | Color group | Class/group dekhna | `hue="passed"` | Ek rang | No |
| `diag_kind` | Diagonal graph | hist ya kde | `diag_kind="kde"` | Auto | No |
| `corner` | Aadha grid | Jagah bachana | `corner=True` | Poora grid | No |
| `kind` | Off-diagonal ki qism | reg, kde | `kind="reg"` | `scatter` | No |
| `height` | Har chhote graph ka size | Size control | `height=2.5` | `2.5` | No |

## 4.10 `regplot` Parameters

| Parameter | Meaning | Kab Use Karein | Example | Na dein to? | Required? |
|---|---|---|---|---|---|
| `x`, `y` | Do numeric columns | Hamesha | `x="study_hours", y="final_marks"` | Graph nahi | Yes |
| `data` | DataFrame | Column names | `data=df` | Names kaam nahi | Practically yes |
| `ci` | Confidence interval | Band hatana/badalna | `ci=None` | 95 | No |
| `order` | Polynomial degree | Curve | `order=2` | 1 (seedhi line) | No |
| `robust` | Outliers ka kam asar | Outliers hon | `robust=True` | False (statsmodels chahiye) | No |
| `lowess` | Smooth flexible curve | Non-linear trend | `lowess=True` | False (statsmodels chahiye) | No |
| `scatter` | Dots dikhana | Sirf line chahiye | `scatter=False` | True | No |
| `scatter_kws` | Dots ki settings | Alpha/size | `scatter_kws={"alpha":0.5}` | Default | No |
| `line_kws` | Line ki settings | Color/width | `line_kws={"color":"red"}` | Default | No |

## 4.11 `violinplot` Parameters

| Parameter | Meaning | Kab Use Karein | Example | Na dein to? | Required? |
|---|---|---|---|---|---|
| `x`, `y` | Numeric (+ category) | Hamesha ek numeric | `x="class", y="final_marks"` | Graph nahi | Yes (numeric) |
| `hue` | Sub-group | Do groups | `hue="gender"` | Ek violin | No |
| `split` | Aadhe aadhe violins | `hue` mein 2 categories | `split=True` | Alag violins | No |
| `inner` | Andar ka nishan | box/quart/point | `inner="quart"` | `box` | No |
| `cut` | Dum ki lambai | Data range par roknna | `cut=0` | 2 | No |
| `density_norm` | Size normalization | Violins barabar | `density_norm="width"` | `area` | No |
| `order` | Tarteeb | Fix tarteeb | `order=[...]` | Default | No |

## 4.12 `plt.subplots` Parameters

| Parameter | Meaning | Example | Na dein to? | Required? |
|---|---|---|---|---|
| `nrows` | Rows | `nrows=2` | 1 | No |
| `ncols` | Columns | `ncols=2` | 1 | No |
| `figsize` | Figure ka size | `figsize=(12, 8)` | Default (6.4, 4.8) | No |
| `sharex`, `sharey` | Axes share karna | `sharex=True` | Alag alag | No |

---

# PART 5: Graph Customization

Professional graphs ke liye title, labels, size, aur colors par dhyan dein.

## 5.1 Customization Functions

| Function | Kaam | Example |
|---|---|---|
| `sns.set_theme()` | Poore graphs ka default style | `sns.set_theme(style="whitegrid", palette="Set2")` |
| `plt.figure(figsize=(w, h))` | Graph ka size | `plt.figure(figsize=(8, 5))` |
| `plt.title()` | Graph ka naam | `plt.title("Average Marks by Class")` |
| `plt.xlabel()` | X-axis ka naam | `plt.xlabel("Class")` |
| `plt.ylabel()` | Y-axis ka naam | `plt.ylabel("Marks (out of 100)")` |
| `plt.xticks(rotation=)` | X-axis labels ghumana | `plt.xticks(rotation=45)` |
| `plt.legend()` | Legend ka control | `plt.legend(title="Gender", loc="upper left")` |
| `plt.grid()` | Grid lines | `plt.grid(axis="y", alpha=0.3)` |
| `palette` | Colors ka set | `palette="Set2"`, `"pastel"`, `"viridis"` |
| `alpha` | Transparency | `alpha=0.6` |
| `markers` / `marker` | Nishan ki shakal | `marker="o"` |
| `linestyle` | Line ki shakal | `linestyle="--"` (dashed) |
| `linewidth` | Line ki motai | `linewidth=2` |
| `plt.tight_layout()` | Overlap hataana | `plt.tight_layout()` |
| `plt.savefig()` | Graph ko file mein save | `plt.savefig("graph.png", dpi=300)` |
| `plt.show()` | Graph dikhana | `plt.show()` |

## 5.2 Complete Customization Example

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_theme(style="whitegrid", palette="Set2")     # 1
df = pd.read_csv("student_performance.csv")

plt.figure(figsize=(9, 6))                           # 2
sns.scatterplot(data=df, x="study_hours", y="final_marks",
                hue="passed", alpha=0.8, s=90)       # 3

plt.title("Study Hours vs Final Marks", fontsize=16, fontweight="bold")   # 4
plt.xlabel("Study Hours per Day (hours)", fontsize=12)                    # 5
plt.ylabel("Final Marks (out of 100)", fontsize=12)                       # 6
plt.grid(alpha=0.3)                                                       # 7
plt.legend(title="Result", loc="lower right")                             # 8
plt.xticks(rotation=0)                                                    # 9
plt.tight_layout()                                                        # 10
plt.savefig("study_vs_marks.png", dpi=300)                                # 11
plt.show()                                                                # 12
```

### Explanation
1. `sns.set_theme(style="whitegrid", palette="Set2")` → Pooray notebook ke liye theme: safed background + grid aur Set2 colors.
2. `plt.figure(figsize=(9, 6))` → Graph ka size 9×6 inch.
3. `sns.scatterplot(... hue="passed", alpha=0.8, s=90)` → Pass/Fail alag color, halki transparency, dot ka size 90.
4. `plt.title(..., fontsize=16, fontweight="bold")` → Bara aur bold title.
5. `plt.xlabel` → X-axis label **unit ke saath** ("hours").
6. `plt.ylabel` → Y-axis label ("out of 100").
7. `plt.grid(alpha=0.3)` → Halki grid taake padhna asaan ho.
8. `plt.legend(title="Result", loc="lower right")` → Legend ka title aur jagah.
9. `plt.xticks(rotation=0)` → X-axis labels seedhe.
10. `plt.tight_layout()` → Overlap se bachata hai.
11. `plt.savefig("study_vs_marks.png", dpi=300)` → Graph ko **PNG file** mein save (dpi = quality). **`savefig` ko `show()` se PEHLE likhein**, warna kabhi kabhi khali image save hoti hai.
12. `plt.show()` → Dikhata hai.

## 5.3 Meaningful Title, Labels Aur Units

| Kharab | Behtar |
|---|---|
| Title: `"Graph 1"` | `"Average Final Marks by Class"` |
| Label: `"x"`, `"y"` | `"Study Hours per Day"`, `"Final Marks (out of 100)"` |
| Unit ghayab | `"Attendance (%)"`, `"Temperature (°C)"` |
| Bohat chhota font | Readable font (12+) |

**Rule:** Jo shakhs graph dekh raha hai woh aap ke bagair bhi samajh sake ke graph kya dikhata hai.

## 5.4 Colors Sirf Decoration Nahi

- **Rang ka matlab hona chahiye:** Pass = hara, Fail = laal (log foran samajh jate hain).
- **Bohat zyada rang** na lagayein (3-5 kafi).
- **Colorblind-friendly** palettes: `"colorblind"`, `"viridis"`.
- Agar sirf ek category compare ho rahi ho, to **ek hi rang** rakhein.
- Heatmap mein **diverging** palette (`coolwarm`) correlation ke liye, **sequential** palette (`Blues`) counts ke liye.

## 5.5 Mashq (Exercise)
Chapter 2 ka bar plot lein aur: (1) title/labels badlein, (2) `xticks(rotation=30)` lagayein, (3) `savefig` se save karein, (4) `palette="colorblind"` lagayein.

---

# PART 6: EDA Workflow — Real Project Mein Kya Order Hota Hai?

## 6.1 Pehle Yeh Samjhein
- **Har dataset par har graph banana zaroori nahi.**
- Graph ka selection **business question** aur **data type** se hota hai.
- EDA ek **order** mein hota hai: pehle data ki sehat, phir akele columns (univariate), phir do (bivariate), phir kai (multivariate).

## 6.2 16 Steps Ka Workflow

| # | Step | Maqsad |
|---|---|---|
| 1 | Business problem samajhna | Kya sawal hal karna hai? |
| 2 | Dataset load karna | Data program mein laana |
| 3 | Rows/columns inspect karna | Data ki shakal |
| 4 | Data types check karna | Numbers numbers hain? |
| 5 | Missing values check karna | Khali cells |
| 6 | Duplicate records check karna | Repeat rows |
| 7 | Invalid values / quality issues | Impossible values |
| 8 | Numerical aur categorical separate karna | Sahi graph chunne ke liye |
| 9 | Descriptive statistics | mean/median/std |
| 10 | Univariate analysis | Ek column |
| 11 | Bivariate analysis | Do columns |
| 12 | Multivariate analysis | Kai columns |
| 13 | Outliers investigate karna | Ajeeb values |
| 14 | Graphs se insights nikalna | Natije |
| 15 | Findings aur limitations | Kya pata, kya nahi pata |
| 16 | Cleaned data aur report save karna | Output |

## 6.3 Pehle Ek "Ganda" (Dirty) Dataset Banate Hain

Asal data aksar saaf nahi hota. Practice ke liye hum apne synthetic dataset ki ek **jaan-boojh kar kharab copy** banate hain.

```python
import pandas as pd
import numpy as np

df = pd.read_csv("student_performance.csv")

dirty = df.copy()                                   # asal data ki copy
dirty.loc[3, "attendance"] = np.nan                 # 1 missing attendance
dirty.loc[12, "attendance"] = np.nan                # 2 missing attendance
dirty.loc[7, "math_marks"] = 150                    # invalid marks (100 se zyada)
dirty = pd.concat([dirty, dirty.iloc[[0]]], ignore_index=True)   # 1 duplicate row
dirty["study_hours"] = dirty["study_hours"].astype(str)          # numbers ko text bana diya

dirty.to_csv("student_performance_dirty.csv", index=False)
print(dirty.shape)
```

**Explanation:**
- `df.copy()` → Asal data ko chhere bagair alag copy.
- `dirty.loc[3, "attendance"] = np.nan` → Row 3 ki attendance ko khali (NaN) kar diya.
- `dirty.loc[7, "math_marks"] = 150` → Ek **ghalat** value (marks 100 se zyada nahi ho sakte).
- `pd.concat([dirty, dirty.iloc[[0]]], ignore_index=True)` → Pehli row ko dobara neeche chipka diya = duplicate.
- `.astype(str)` → `study_hours` ko text bana diya (jaise `"5.2"`). Asal projects mein CSV mein aisa kabhi kabhi hota hai.
- **Expected output:** `(41, 12)` (40 + 1 duplicate row).

## 6.4 Steps 2-9: Data Ko Samajhna

```python
import pandas as pd

# Step 2: Load
dirty = pd.read_csv("student_performance_dirty.csv")

# Step 3: Shakal
print(dirty.shape)             # (41, 12)
print(dirty.head())

# Step 4: Data types
print(dirty.dtypes)

# Step 5: Missing values
print(dirty.isnull().sum())

# Step 6: Duplicates
print("Duplicates:", dirty.duplicated().sum())

# Step 7: Invalid values
print("Marks > 100:", (dirty["math_marks"] > 100).sum())
print("Attendance < 0 ya > 100:", ((dirty["attendance"] < 0) | (dirty["attendance"] > 100)).sum())

# Step 8: Numerical aur categorical separate
numeric_cols = dirty.select_dtypes(include="number").columns.drop("student_id")
categorical_cols = ["gender", "class", "passed", "city"]
print("Numeric:", list(numeric_cols))

# Step 9: Descriptive statistics
print(dirty[numeric_cols].describe().round(2))
```

**Expected results aur explanation:**
- `dirty.shape` → `(41, 12)`.
- Is dirty file mein `study_hours` ab text hai? Jab CSV dobara read hoti hai to pandas `"5.2"` ko wapas number bana deta hai. (Asal masla tab hota hai jab column mein `"five"` jaisa text ho.) Agar kabhi `dtypes` mein `object`/`str` aaye jahan number hona chahiye, to `pd.to_numeric(col, errors="coerce")` se theek karein.
- `isnull().sum()` → `attendance` mein **2** missing values.
- `duplicated().sum()` → **1** duplicate.
- `Marks > 100` → **1** (humari 150 wali).
- `select_dtypes(include="number").columns.drop("student_id")` → ID ke ilawa numeric columns.
- `describe()` → `math_marks` ka **max 150** nazar aayega; yeh **red flag** hai.

## 6.5 Data Cleaning (Step 5-7 Ka Hal)

```python
import pandas as pd

dirty = pd.read_csv("student_performance_dirty.csv")
clean = dirty.copy()

# 1) Duplicates hatao
clean = clean.drop_duplicates()

# 2) Invalid marks ko NaN banao
clean.loc[clean["math_marks"] > 100, "math_marks"] = pd.NA

# 3) Missing values: median se bharo
clean["attendance"] = clean["attendance"].fillna(clean["attendance"].median())
clean["math_marks"] = clean["math_marks"].fillna(clean["math_marks"].median())

# 4) Number columns ko sahi type dein
clean["study_hours"] = pd.to_numeric(clean["study_hours"], errors="coerce")

# 5) final_marks dobara hisaab (math theek ho gaya)
clean["final_marks"] = (0.4 * clean["math_marks"] + 0.3 * clean["science_marks"]
                        + 0.3 * clean["english_marks"]).round(1)
clean["passed"] = clean["final_marks"].apply(lambda m: "Pass" if m >= 40 else "Fail")

print(clean.shape)
print(clean.isnull().sum().sum())
clean.to_csv("student_performance_clean.csv", index=False)
```

**Line-by-line:**
- `drop_duplicates()` → Poori tarah repeat hui rows hata deta hai. Ab `(40, 12)`.
- `clean.loc[condition, "col"] = pd.NA` → Jahan math marks 100 se zyada hon wahan value ko "khali" kar do (kyun ke woh ghalat hai).
- `fillna(median)` → Khali jagah **median** se bharo. **Median** is liye ke outliers se kam mutassir hota hai. **Yaad rakhein:** Missing values bharna ek **faisla** hai; asal project mein is ki wajah likhni chahiye.
- `pd.to_numeric(col, errors="coerce")` → Text ko number banata hai; jo number nahi ban sake use `NaN` kar deta hai.
- `final_marks` ko dobara hisaab kiya kyun ke math marks theek hue.
- `clean.isnull().sum().sum()` → Poore DataFrame mein total missing = `0` hona chahiye.
- `to_csv(...)` → Saaf data save kiya (Step 16).

> **Zaroori:** Cleaning mein **asal data file ko overwrite na karein**. Hamesha nayi file mein save karein.

## 6.6 Steps 10-14: Graphs Se Samajhna

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_theme(style="whitegrid")
df = pd.read_csv("student_performance_clean.csv")

# Step 10: Univariate (ek column)
fig, axes = plt.subplots(1, 3, figsize=(15, 4))
sns.histplot(df["final_marks"], bins=8, kde=True, ax=axes[0])
axes[0].set_title("Final Marks Distribution")
sns.boxplot(y=df["attendance"], ax=axes[1])
axes[1].set_title("Attendance Box Plot")
sns.countplot(data=df, x="passed", hue="passed", legend=False, ax=axes[2])
axes[2].set_title("Pass vs Fail")
fig.tight_layout()
plt.show()

# Step 11: Bivariate (do columns)
fig, axes = plt.subplots(1, 3, figsize=(16, 4.5))
sns.scatterplot(data=df, x="study_hours", y="final_marks", ax=axes[0])
axes[0].set_title("Study Hours vs Marks")
sns.scatterplot(data=df, x="attendance", y="final_marks", ax=axes[1])
axes[1].set_title("Attendance vs Marks")
sns.barplot(data=df, x="class", y="final_marks", order=["Class 8", "Class 9", "Class 10"],
            hue="class", legend=False, errorbar=None, ax=axes[2])
axes[2].set_title("Average Marks by Class")
fig.tight_layout()
plt.show()

# Step 12: Multivariate (kai columns)
cols = ["study_hours", "attendance", "math_marks", "final_marks"]
sns.heatmap(df[cols].corr(), annot=True, cmap="coolwarm", fmt=".2f", vmin=-1, vmax=1)
plt.title("Correlation Heatmap")
plt.tight_layout()
plt.show()

g = sns.pairplot(df, vars=cols, hue="passed", corner=True)
plt.show()

# Step 13: Outliers (IQR rule)
for col in ["study_hours", "attendance", "final_marks"]:
    q1, q3 = df[col].quantile([0.25, 0.75])
    iqr = q3 - q1
    low, high = q1 - 1.5 * iqr, q3 + 1.5 * iqr
    n_out = ((df[col] < low) | (df[col] > high)).sum()
    print(f"{col}: outliers = {n_out}")
```

**Explanation:**
- **Univariate** = ek hi column. `histplot` shakal, `boxplot` median/outliers, `countplot` categories.
- **Bivariate** = do columns. `scatterplot` do numeric, `barplot` category + numeric.
- **Multivariate** = kai columns ek saath. `heatmap` aur `pairplot`.
- `q1, q3 = df[col].quantile([0.25, 0.75])` → Ek hi line mein dono quartiles.
- `for col in [...]` → Har column par wahi outlier check dohrata hai.
- `f"{col}: outliers = {n_out}"` → **f-string**: `{}` ke andar variable ki value likh dete hain.
- `fig, axes = plt.subplots(1, 3...)` → 3 graphs ek line mein (Chapter 11 se).

## 6.7 Steps 15-16: Findings Aur Report Save Karna

```python
import pandas as pd

df = pd.read_csv("student_performance_clean.csv")

report = f"""
# Student Performance EDA Report (Synthetic Data)

- Rows: {df.shape[0]}, Columns: {df.shape[1]}
- Average final marks: {df['final_marks'].mean():.1f}
- Pass: {(df['passed'] == 'Pass').sum()}, Fail: {(df['passed'] == 'Fail').sum()}
- Correlation (study_hours, final_marks): {df['study_hours'].corr(df['final_marks']):.2f}

## Limitations
- Sirf {df.shape[0]} students; synthetic data.
- Correlation ka matlab causation nahi.
"""

with open("eda_report.md", "w", encoding="utf-8") as f:
    f.write(report)
print(report)
```

**Explanation:**
- `f"""..."""` → Multi-line f-string; `{...}` mein Python calculations.
- `:.1f` → 1 decimal tak. `:.2f` → 2 decimal tak.
- `open("eda_report.md", "w", encoding="utf-8")` → File **write mode** mein kholi. `utf-8` har zubaan ke liye theek.
- `with ... as f:` → File kaam ke baad khud band ho jati hai.
- `f.write(report)` → Text file mein likha.

**Expected result:** Ek `eda_report.md` file banti hai jis mein rows, average, pass/fail aur limitations likhi hoti hain.

---
# PART 7: Complete Real-World EDA Project — Student Performance Analysis

> **Kaise chalayein:** Is project ke saare code blocks **ek hi Jupyter Notebook ke cells** hain. Unhein **upar se neeche order mein** chalayein, kyun ke baad wale cells pichle cells ke variables (`df`, `monthly`) use karte hain.
>
> **Dobara yaad dehani:** Data **synthetic (practice)** hai, asal school ka nahi. Neeche jo numbers likhe hain woh isi course ke dataset (seed 42) ke hain. Agar aap ka dataset alag ho to aap ke numbers thore alag honge; apne output ko parh kar apne conclusions likhein.

---

## Section 1: Problem Statement

**Scenario:** Ek school ki principal ne 40 students ka data diya hai. Woh chahti hain ke aap data dekh kar unke in sawalon ka jawab dein:

1. Average marks kitne hain?
2. Sab se achhi performance kis subject mein hai?
3. Study hours aur final marks mein kya relationship hai?
4. Attendance aur marks mein kya relationship hai?
5. Kis class ke marks zyada hain?
6. Pass aur fail students kitne hain?
7. Marks ki distribution kaisi hai?
8. Kya koi unusual marks ya outliers hain?
9. Kaun se numerical features ek doosre ke saath related hain?

**Hamari strategy:** Har sawal ke liye **sahi graph** chunenge (sab graphs zabardasti nahi banayenge).

| Sawal | Graph |
|---|---|
| 1, 2 | Bar plot (subject-wise average) + `describe()` |
| 3, 4 | Scatter plot + Regression plot |
| 5 | Bar plot + Box plot + Violin plot |
| 6 | Count plot |
| 7 | Histogram |
| 8 | Box plot + IQR rule + Scatter |
| 9 | Heatmap + Pairplot |
| Waqt ka trend | Line plot (**sirf alag monthly dataset par**) |

> Hamare student dataset mein **time column nahi hai**, is liye us par line plot nahi banayenge. Line plot ke liye `monthly_performance.csv` use hogi.

## Section 2: Imports

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_theme(style="whitegrid", palette="Set2")
pd.set_option("display.max_columns", None)     # sab columns dikhao
```

- Pehli 4 lines libraries laati hain.
- `sns.set_theme(...)` → Poore project ka style.
- `pd.set_option("display.max_columns", None)` → `print` karte waqt pandas columns ko `...` se chhupaye na.

## Section 3: Dataset Creation / Loading

Agar `student_performance.csv` aur `monthly_performance.csv` aap ke paas nahi hain, to pehle **Section 2.2** (student) aur **Chapter 1 Step A** (monthly) wala code chalayein.

```python
import os

# Safety check: file mojood hai?
for f in ["student_performance.csv", "monthly_performance.csv"]:
    print(f, "->", "mil gayi" if os.path.exists(f) else "NAHI MILI (pehle create karein)")

df = pd.read_csv("student_performance.csv")
monthly = pd.read_csv("monthly_performance.csv")
print(df.shape, monthly.shape)
```

- `os.path.exists(f)` → File maujood hai to `True`.
- `"mil gayi" if ... else "NAHI MILI"` → Ek line ka if-else.
- Expected output: `(40, 12) (18, 3)`.

## Section 4: Initial Inspection

```python
print(df.head())
print(df.info())
print(df.isnull().sum())
print("Duplicates:", df.duplicated().sum())
print(df["class"].value_counts())
print(df["passed"].value_counts())
```

- `head()` → Pehli 5 rows.
- `info()` → Columns, types, non-null counts.
- `isnull().sum()` → Har column mein missing values.
- `duplicated().sum()` → Duplicate rows.
- `value_counts()` → Categories ki tadaad.

**Expected:** Koi missing value nahi (sab 0), 0 duplicates. Class counts: Class 10 = 17, Class 9 = 12, Class 8 = 11. Pass = 33, Fail = 7.

## Section 5: Data Cleaning

Humara data pehle se saaf hai, lekin **hamesha** kuch quality checks chalayein:

```python
# Marks 0-100 ke andar hone chahiye
mark_cols = ["math_marks", "science_marks", "english_marks", "final_marks"]
invalid_marks = ((df[mark_cols] < 0) | (df[mark_cols] > 100)).sum()
print("Invalid marks:\n", invalid_marks)

# Attendance 0-100
print("Invalid attendance:", ((df["attendance"] < 0) | (df["attendance"] > 100)).sum())

# Study hours negative to nahi?
print("Invalid study hours:", (df["study_hours"] < 0).sum())

# Text columns ki safai (extra space ya case farq)
for col in ["gender", "class", "passed", "city"]:
    df[col] = df[col].str.strip()

print("Cleaning mukammal. Shape:", df.shape)
```

- `df[mark_cols] < 0` → Har marks column mein check ke 0 se kam to nahi.
- `| ` → "ya". Dono conditions mein se ek bhi sach ho to `True`.
- `.sum()` → Kitni ghalat values. Expected: sab `0`.
- `.str.strip()` → Text ke aage peeche ke faltu spaces hata deta hai (jaise `"Male "` ko `"Male"`). Agar spaces hon to `"Male"` aur `"Male "` do alag categories ban jati hain.

## Section 6: Numerical Analysis

```python
numeric_cols = ["study_hours", "attendance", "math_marks",
                "science_marks", "english_marks", "final_marks"]

print(df[numeric_cols].describe().round(2))

subject_avg = df[["math_marks", "science_marks", "english_marks"]].mean().round(1)
print("\nSubject-wise average:\n", subject_avg)
print("\nSab se achha subject:", subject_avg.idxmax(), "->", subject_avg.max())

print("\nAverage final marks:", round(df["final_marks"].mean(), 1))
print("Median final marks :", df["final_marks"].median())
```

- `describe()` → Count, mean, std, min, quartiles, max.
- `df[[...]].mean()` → 3 subjects ka average ek saath. Dhyan dein: **double bracket `[[...]]`** jab kai columns chunne hon.
- `.idxmax()` → Sab se bari value ka **naam (index)**. Yahan subject ka naam.
- `.max()` → Sab se bari value.

**Expected results:**
- Math ≈ **57.9**, Science ≈ **58.8**, English ≈ **60.1** → **English** sab se behtar average.
- Average final marks ≈ **58.8**, median ≈ **62.2**. **Median average se thora zyada** hai, jo halki si left-skew (kam marks wale students) ki taraf ishara hai.
- Average study hours ≈ 4.6, average attendance ≈ 76%.

> **Sawal 1 aur 2 ka jawab mil gaya.**

## Section 7: Categorical Analysis

```python
print(df.groupby("class")["final_marks"].agg(["mean", "median", "count"]).round(1))
print()
print(df.groupby("gender")["final_marks"].mean().round(1))
print()
print(pd.crosstab(df["class"], df["passed"]))
print()
print(pd.crosstab(df["class"], df["passed"], normalize="index").round(2) * 100)
```

- `groupby("class")["final_marks"].agg([...])` → Har class ke liye mean, median, count.
- `pd.crosstab(a, b)` → Do categorical columns ki **cross table** (kitne Class 8 Pass, kitne Class 8 Fail...).
- `normalize="index"` → Har row ko **percentage** mein badalta hai (row ka jama 100%).

**Expected results (approximately):**

| Class | Mean | Median | Students |
|---|---|---|---|
| Class 10 | 60.5 | 66.9 | 17 |
| Class 8 | 58.9 | 56.7 | 11 |
| Class 9 | 56.2 | 62.2 | 12 |

- Fail percentage: Class 8 ≈ 9%, Class 9 = 25%, Class 10 ≈ 18%.
- Gender: Female ≈ 60.0, Male ≈ 57.6.

## Section 8: Individual Graphs

### 8.1 Line Plot — Waqt Ka Trend (monthly data par)

```python
plt.figure(figsize=(8, 5))
sns.lineplot(data=monthly, x="month", y="avg_marks", hue="class",
             style="class", marker="o", errorbar=None)
plt.title("Monthly Average Marks by Class (Synthetic Data)")
plt.xlabel("Month")
plt.ylabel("Average Marks")
plt.tight_layout()
plt.show()
```
**Explanation:** `x="month"` waqt, `y="avg_marks"` kya naapna hai, `hue`/`style` har class ki alag line. **Insight:** January se June tak teeno classes ka average barha hai (jaise Class 8: 52 → 66).

### 8.2 Bar Plot — Class aur Subject

```python
order = ["Class 8", "Class 9", "Class 10"]

fig, axes = plt.subplots(1, 2, figsize=(13, 5))

sns.barplot(data=df, x="class", y="final_marks", order=order,
            hue="class", legend=False, errorbar=("ci", 95), ax=axes[0])
axes[0].set_title("Average Final Marks by Class")
axes[0].set_xlabel("Class")
axes[0].set_ylabel("Average Final Marks")

subject_long = df.melt(value_vars=["math_marks", "science_marks", "english_marks"],
                       var_name="subject", value_name="marks")
sns.barplot(data=subject_long, x="subject", y="marks",
            hue="subject", legend=False, errorbar=None, ax=axes[1])
axes[1].set_title("Average Marks by Subject")
axes[1].set_xlabel("Subject")
axes[1].set_ylabel("Average Marks")

fig.tight_layout()
plt.show()
```
- `df.melt(...)` → **Wide table ko long table** mein badalta hai. Teen columns (math, science, english) ek column `subject` aur ek column `marks` ban jate hain. Seaborn ko aksar long format pasand hota hai.
- `var_name`, `value_name` → Naye columns ke naam.
- **Insight:** English ka average sab se zyada, math sab se kam. Class 10 ka average sab se zyada, lekin error bars aapas mein overlap karte hain.

### 8.3 Scatter Plot — Study Hours aur Attendance

```python
fig, axes = plt.subplots(1, 2, figsize=(13, 5))

sns.scatterplot(data=df, x="study_hours", y="final_marks", hue="passed",
                alpha=0.8, s=70, ax=axes[0])
axes[0].set_title("Study Hours vs Final Marks")
axes[0].set_xlabel("Study Hours per Day")
axes[0].set_ylabel("Final Marks")

sns.scatterplot(data=df, x="attendance", y="final_marks", hue="passed",
                alpha=0.8, s=70, ax=axes[1])
axes[1].set_title("Attendance vs Final Marks")
axes[1].set_xlabel("Attendance (%)")
axes[1].set_ylabel("Final Marks")

fig.tight_layout()
plt.show()

print("Corr study_hours vs final_marks:", round(df["study_hours"].corr(df["final_marks"]), 2))
print("Corr attendance vs final_marks :", round(df["attendance"].corr(df["final_marks"]), 2))
```
**Insight:** Dono graphs mein dots upar ki taraf jate hain. Correlation: study hours ≈ **0.67**, attendance ≈ **0.59**. Yani study hours ka rishta thora zyada mazboot hai. **Yeh wajah (cause) nahi, sirf rishta hai.**

### 8.4 Regression Plot — Trend Line

```python
plt.figure(figsize=(7, 5))
sns.regplot(data=df, x="study_hours", y="final_marks",
            scatter_kws={"alpha": 0.7}, line_kws={"color": "red"})
plt.title("Study Hours vs Final Marks with Trend Line")
plt.xlabel("Study Hours per Day")
plt.ylabel("Final Marks")
plt.tight_layout()
plt.show()

slope, intercept = np.polyfit(df["study_hours"], df["final_marks"], 1)
print(f"Slope = {slope:.2f}  (har extra ghante par lagbhag itne marks)")
```
**Insight:** Slope ≈ **5.5** — is sample mein har extra study hour ke saath average final marks lagbhag 5.5 barhte nazar aate hain. Do students line se bohat door hain (neeche outliers wala section dekhein).

### 8.5 Histogram — Marks Ki Distribution

```python
plt.figure(figsize=(7, 5))
sns.histplot(data=df, x="final_marks", bins=8, kde=True)
plt.axvline(df["final_marks"].mean(), color="red", linestyle="--", label="Mean")
plt.axvline(df["final_marks"].median(), color="green", linestyle="-", label="Median")
plt.title("Distribution of Final Marks")
plt.xlabel("Final Marks")
plt.ylabel("Number of Students")
plt.legend()
plt.tight_layout()
plt.show()

print("Skewness:", round(df["final_marks"].skew(), 2))
```
- `plt.axvline(x, ...)` → Graph par **khari (vertical) line** lagata hai. Mean aur median ko dikhane ke liye.
- **Insight:** Skewness ≈ **-0.23** (halki left-skew). Sab se zyada students (40 mein se 18) 50-70 marks ki range mein hain. Mean (58.8) median (62.2) se thora kam hai, jo kam marks wale students ki wajah se hai.

### 8.6 Box Plot aur Violin Plot — Class-wise Comparison

```python
fig, axes = plt.subplots(1, 2, figsize=(13, 5))

sns.boxplot(data=df, x="class", y="final_marks", order=order,
            hue="class", legend=False, ax=axes[0])
axes[0].set_title("Box Plot: Final Marks by Class")

sns.violinplot(data=df, x="class", y="final_marks", order=order,
               hue="class", legend=False, cut=0, inner="quart", ax=axes[1])
axes[1].set_title("Violin Plot: Final Marks by Class")

for ax in axes:
    ax.set_xlabel("Class")
    ax.set_ylabel("Final Marks")

fig.tight_layout()
plt.show()
```
- `for ax in axes:` → Dono axes par ek jaisi labels ek hi loop se lagayi.
- **Insight:** Class 10 ka median sab se zyada (~66.9), Class 8 ka sab se kam (~56.7). Har class ke andar marks ka phailao bara hai (~15-18 marks ka standard deviation), yani **ek class ke andar farq, classes ke darmiyan farq se zyada hai.**

### 8.7 Count Plot — Pass/Fail

```python
fig, axes = plt.subplots(1, 2, figsize=(12, 5))

ax1 = sns.countplot(data=df, x="passed", order=["Pass", "Fail"],
                    hue="passed", palette={"Pass": "seagreen", "Fail": "tomato"},
                    legend=False, ax=axes[0])
for container in ax1.containers:
    ax1.bar_label(container)
axes[0].set_title("Pass vs Fail Count")
axes[0].set_xlabel("Result")
axes[0].set_ylabel("Number of Students")

sns.countplot(data=df, x="class", hue="passed", order=order, ax=axes[1])
axes[1].set_title("Pass/Fail by Class")
axes[1].set_xlabel("Class")
axes[1].set_ylabel("Number of Students")

fig.tight_layout()
plt.show()
```
- `for container in ax1.containers: ax1.bar_label(container)` → Har bar ke upar number likhta hai (loop se, taake index ki ghalti na ho).
- **Insight:** **33 Pass, 7 Fail** (82.5% pass). Fail students zyada tar kam study hours wale hain.

### 8.8 Heatmap — Correlation

```python
corr = df[numeric_cols].corr()

plt.figure(figsize=(8, 6))
mask = np.triu(np.ones_like(corr, dtype=bool))
sns.heatmap(corr, mask=mask, annot=True, fmt=".2f", cmap="coolwarm",
            vmin=-1, vmax=1, linewidths=0.5, square=True)
plt.title("Correlation Heatmap")
plt.tight_layout()
plt.show()
```
**Insight:** Saare columns aapas mein **positive** related hain. `final_marks` math/science/english se bohat zyada related hai **kyun ke woh unhi se bana hai** (is ko "discovery" na samjhein). Study hours ↔ attendance ≈ 0.63; yani jo zyada parhte hain unki attendance bhi aam tor par behtar.

### 8.9 Pairplot — Chune Hue Columns

```python
g = sns.pairplot(df, vars=["study_hours", "attendance", "final_marks"],
                 hue="passed", diag_kind="hist", corner=True)
g.figure.suptitle("Pairplot: Key Features", y=1.02)
plt.show()
```
**Insight:** 3 columns kafi hain. Fail students neeche-left mein jama hain (kam study hours, kam marks). **Dhyan dein:** Fail ka matlab hi `final_marks < 40` hai, is liye final_marks par alag hona definition ka asar hai.

## Section 8.10: Outliers Ki Tehqeeq

```python
def iqr_outliers(data, col):
    q1, q3 = data[col].quantile([0.25, 0.75])
    iqr = q3 - q1
    low, high = q1 - 1.5 * iqr, q3 + 1.5 * iqr
    return data[(data[col] < low) | (data[col] > high)], low, high

for col in ["final_marks", "study_hours", "attendance"]:
    out, low, high = iqr_outliers(df, col)
    print(f"{col}: fences = ({low:.1f}, {high:.1f}), outliers = {len(out)}")

# Relationship ke hisaab se unusual students
unusual = df[((df["study_hours"] < 2) & (df["final_marks"] > 80)) |
             ((df["study_hours"] > 7) & (df["final_marks"] < 40))]
print(unusual[["student_name", "study_hours", "attendance", "final_marks", "passed"]])
```

- `def iqr_outliers(data, col):` → **Function** banaya jo kisi bhi column ke IQR outliers deta hai. `def` = function define. Function ko baar baar likhne ke bajaye ek baar likh kar dobara dobara istemal karte hain.
- `return data[...], low, high` → Function **teen cheezein** wapas karta hai.
- `out, low, high = iqr_outliers(df, col)` → Teeno cheezein alag alag variables mein.
- `unusual = df[(...) | (...)]` → Do conditions: **kam study + zyada marks** YA **zyada study + kam marks**.

**Expected results:**
- `final_marks` aur `study_hours` mein IQR rule se **koi outlier nahi** mila. `attendance` mein **1 potential outlier** mila (98% attendance, jo upper fence 94.5 se thori zyada hai). Yeh ghalat data nahi, bas ek bahut achhi attendance hai.
- Lekin `unusual` mein **do students** aate hain: **Hamza Sheikh** (1.0 ghanta study, ~87.7 marks) aur **Maryam Aslam** (8.0 ghante study, ~30.9 marks).
- **Faisla:** Yeh ghalat data nahi lagta; yeh **unusual cases** hain. Asal school mein hum **un se pooch kar** wajah dhoondhte (pehle se tez? tabiyat kharab? data entry ghalti?). Hum inhein **delete nahi karte** jab tak wajah saabit na ho.

## Section 9: Combined Dashboard

```python
fig, axes = plt.subplots(2, 3, figsize=(18, 10))

sns.lineplot(data=monthly, x="month", y="avg_marks", hue="class",
             marker="o", errorbar=None, ax=axes[0, 0])
axes[0, 0].set_title("Monthly Average Marks")
axes[0, 0].set_xlabel("Month")
axes[0, 0].set_ylabel("Average Marks")

sns.barplot(data=df, x="class", y="final_marks", order=order,
            hue="class", legend=False, errorbar=None, ax=axes[0, 1])
axes[0, 1].set_title("Average Final Marks by Class")
axes[0, 1].set_xlabel("Class")
axes[0, 1].set_ylabel("Average Final Marks")

sns.countplot(data=df, x="passed", order=["Pass", "Fail"],
              hue="passed", legend=False, ax=axes[0, 2])
axes[0, 2].set_title("Pass vs Fail")
axes[0, 2].set_xlabel("Result")
axes[0, 2].set_ylabel("Number of Students")

sns.histplot(data=df, x="final_marks", bins=8, kde=True, ax=axes[1, 0])
axes[1, 0].set_title("Final Marks Distribution")
axes[1, 0].set_xlabel("Final Marks")
axes[1, 0].set_ylabel("Number of Students")

sns.scatterplot(data=df, x="study_hours", y="final_marks", hue="passed", ax=axes[1, 1])
axes[1, 1].set_title("Study Hours vs Final Marks")
axes[1, 1].set_xlabel("Study Hours")
axes[1, 1].set_ylabel("Final Marks")

sns.boxplot(data=df, x="class", y="final_marks", order=order,
            hue="class", legend=False, ax=axes[1, 2])
axes[1, 2].set_title("Final Marks by Class")
axes[1, 2].set_xlabel("Class")
axes[1, 2].set_ylabel("Final Marks")

fig.suptitle("Student Performance Dashboard (Synthetic Data)", fontsize=18, fontweight="bold")
fig.tight_layout()
fig.savefig("student_dashboard.png", dpi=200)
plt.show()
```

- `plt.subplots(2, 3, ...)` → 2 rows × 3 columns = 6 graphs. Index: `axes[row, col]`.
- Har graph `ax=axes[r, c]` se apni jagah par bana, aur `set_title/set_xlabel/set_ylabel` se label hue.
- `fig.suptitle(...)` → Poore dashboard ka title.
- `fig.savefig("student_dashboard.png", dpi=200)` → Dashboard ko image file mein save kiya (principal ko bhejne ke liye).

## Section 10: Insights (Data Se Samjhi Hui Baatein)

Sawal-wise jawab (synthetic data ke mutabiq):

| # | Sawal | Jawab |
|---|---|---|
| 1 | Average marks | Average final marks ≈ **58.8**, median ≈ **62.2** |
| 2 | Best subject | **English** (avg ≈ 60.1), phir Science (≈ 58.8), phir Math (≈ 57.9) |
| 3 | Study hours vs marks | Positive relationship (corr ≈ **0.67**); slope ≈ 5.5 marks per hour |
| 4 | Attendance vs marks | Positive relationship (corr ≈ **0.59**) |
| 5 | Kis class ke marks zyada | Average mein **Class 10** (≈ 60.5), lekin farq chhota hai aur error bars overlap karte hain |
| 6 | Pass/Fail | **33 Pass (82.5%)**, **7 Fail (17.5%)** |
| 7 | Distribution | Halki left-skewed (skewness ≈ -0.23); sab se zyada students 50-70 mein |
| 8 | Outliers | `final_marks` mein IQR rule se **koi outlier nahi** (attendance mein sirf 1 potential outlier: 98%), lekin do students (Hamza, Maryam) study-hours ke rishte ke hisaab se **unusual** |
| 9 | Related features | Study hours, attendance, aur subject marks aapas mein positive related; `final_marks` subjects se is liye strongly related ke woh unka formula hai |

## Section 11: Conclusion

- Is synthetic school data mein **zyada study hours aur behtar attendance wale students ke marks aam tor par zyada** hain.
- **Zyadatar students pass hain (82.5%)**; fail students ki study hours aur attendance kam hain.
- **English** sab se mazboot subject hai, **Math** sab se kamzor (average ke hisaab se).
- Classes ke darmiyan average farq **chhota** hai; classes ke **andar** farq zyada hai.
- Do unusual students ki alag tehqeeq honi chahiye.

## Section 12: Limitations (Hadood)

1. **Chhota sample:** Sirf 40 students (har class mein 11-17). Nateeje pakke nahi.
2. **Synthetic data:** Study hours aur marks ka rishta humne khud code se banaya hai; asal school mein farq ho sakta hai.
3. **Correlation ≠ causation:** Hum nahi keh sakte ke study hours marks "paida" karte hain.
4. **Missing factors:** Pichli taleem, teacher, ghar ka mahol, sehat data mein nahi hain.
5. **`final_marks` ek formula hai:** Is ka subjects se strong correlation natural hai.
6. **Line plot ka data alag aur chhota** hai (har class ka mahine mein ek hi average).

## Section 13: Next Steps

1. Asal school ka (anonymized) data collect karein.
2. Zyada students aur zyada features (parents' education, tuition, sleep hours) shamil karein.
3. Statistical tests (t-test, ANOVA) se classes ke farq ko parkhein.
4. **Alag se** train/test split ke saath Machine Learning model (jaise Linear Regression) banayein.
5. Dashboard ko **Streamlit** ya Power BI mein interactive banayein.

---
# PART 8: Additional Practice Datasets (5 Datasets)

> ⚠️ **Yeh sab datasets synthetic (code se banaye gaye practice data) hain.** Yeh kisi asal school, dukaan, hospital, online store ya mausam station ka real record **nahi** hain. Inka maqsad sirf graphs aur EDA ki mashq hai. Asal projects mein aap apna real data (CSV/Excel/database) use karenge.

| # | Dataset | File |
|---|---|---|
| 1 | Student Performance | `student_performance.csv` (Section 2.2) |
| 2 | Sales and Business | `sales_data.csv` |
| 3 | Hospital and Patient Visits | `hospital_visits.csv` |
| 4 | E-commerce Products and Orders | `ecommerce_orders.csv` |
| 5 | Weather and Temperature | `weather_data.csv` |

---

## Dataset 1: Student Performance (Dobara Jaiza)

**Columns:** `student_id, student_name, gender, class, study_hours, attendance, math_marks, science_marks, english_marks, final_marks, passed, city`

**Business questions:**
- Kis city ke students ka average behtar hai?
- Kya science marks aur math marks ka rishta mazboot hai?
- Gender ke hisaab se study hours mein farq hai?

**Suitable graphs:** Bar plot (city-wise average), scatter/regplot (math vs science), box plot (gender vs study hours).

**Practice exercise:** `math_marks` vs `science_marks` ka regplot banayein aur correlation number print karein. Phir `city` ka count plot banayein aur batayein kaun si city mein sab se kam students hain.

---

## Dataset 2: Sales and Business

### Dataset Banayein (Synthetic)

```python
import numpy as np
import pandas as pd

np.random.seed(7)
n = 300

dates = pd.date_range("2025-01-01", periods=n, freq="D")
region = np.random.choice(["North", "South", "East", "West"], n)
product = np.random.choice(["Shoes", "Bags", "Watches", "Shirts"], n)
marketing_spend = np.round(np.random.uniform(500, 5000, n), 0)
units = np.round(5 + marketing_spend / 250 + np.random.normal(0, 3, n)).clip(min=1)
price_map = {"Shoes": 80, "Bags": 60, "Watches": 150, "Shirts": 40}
price = pd.Series(product).map(price_map).to_numpy()
sales = units * price

sales_df = pd.DataFrame({
    "date": dates,
    "region": region,
    "product": product,
    "marketing_spend": marketing_spend,
    "units_sold": units,
    "unit_price": price,
    "sales": sales,
})
sales_df["month"] = sales_df["date"].dt.strftime("%Y-%m")
sales_df.to_csv("sales_data.csv", index=False)
print(sales_df.head())
print(sales_df.shape)
```

**Explanation:**
- `pd.date_range("2025-01-01", periods=n, freq="D")` → 300 din ki date list.
- `marketing_spend` → Random kharcha. `units` → Kharche ke saath barhti hui units + thora noise (taake relationship ho).
- `.clip(min=1)` → Units 1 se kam na hon.
- `pd.Series(product).map(price_map)` → Har product ka price dictionary se.
- `sales = units * price` → Total sales.
- `dt.strftime("%Y-%m")` → Date se "2025-01" jaisa month nikalta hai.

**Business questions:**
- Mahine ba mahine sales ka trend kaisa hai?
- Kis region mein sales zyada hain?
- Kis product se sab se zyada sales aati hain?
- Kya marketing spend aur sales ka rishta hai?

**Suitable graphs:** Line plot (monthly sales), bar plot (region/product-wise), scatter/regplot (marketing vs sales), box plot (product-wise sales), heatmap (numeric correlation).

**Practice exercise:**
```python
monthly_sales = sales_df.groupby("month")["sales"].sum().reset_index()
# Ab sns.lineplot(data=monthly_sales, x="month", y="sales", marker="o") banayein
# aur x-axis labels ko plt.xticks(rotation=45) se ghumayein.
```
`groupby("month")["sales"].sum()` har mahine ki total sales deta hai, `reset_index()` use wapas DataFrame banata hai.

---

## Dataset 3: Hospital and Patient Visits

### Dataset Banayein (Synthetic)

```python
import numpy as np
import pandas as pd

np.random.seed(11)
n = 250

department = np.random.choice(["Emergency", "Cardiology", "Orthopedics", "Pediatrics", "General"], n,
                              p=[0.25, 0.15, 0.15, 0.2, 0.25])
age = np.where(department == "Pediatrics", np.random.randint(1, 15, n), np.random.randint(15, 85, n))
wait_time = np.round(np.random.gamma(shape=2.5, scale=12, size=n) +
                     np.where(department == "Emergency", 10, 0), 0)
bill_amount = np.round(np.random.normal(5000, 1500, n) +
                       np.where(department == "Cardiology", 6000, 0) +
                       np.where(department == "Orthopedics", 3000, 0)).clip(min=500)
satisfaction = np.clip(np.round(4.5 - wait_time / 40 + np.random.normal(0, 0.6, n)), 1, 5).astype(int)

hospital_df = pd.DataFrame({
    "patient_id": range(1, n + 1),
    "age": age,
    "gender": np.random.choice(["Male", "Female"], n),
    "department": department,
    "wait_time_min": wait_time,
    "bill_amount": bill_amount,
    "satisfaction": satisfaction,
})
hospital_df.to_csv("hospital_visits.csv", index=False)
print(hospital_df.head())
```

**Explanation:**
- `np.where(condition, a, b)` → Agar condition sach to `a`, warna `b`. Yahan Pediatrics mein bachon ki umar.
- `np.random.gamma(...)` → Aisi distribution jo right-skewed hoti hai (waiting time mein aksar aisa hota hai).
- `satisfaction` → Zyada wait ka matlab kam satisfaction (1 se 5), noise ke saath.

**Business questions:**
- Kis department mein patients zyada aate hain?
- Waiting time ki distribution kaisi hai?
- Kya zyada wait ka matlab kam satisfaction hai?
- Kis department ka average bill zyada hai?

**Suitable graphs:** Count plot (department-wise patients), histogram (wait time, right-skewed), scatter/regplot (wait vs satisfaction), box plot (department-wise bill), bar plot (average bill).

**Practice exercise:** Waiting time ka histogram banayein aur batayein ke distribution left-skewed hai ya right-skewed. Phir `department` ke mutabiq `wait_time_min` ka box plot banayein aur dekhein kis department mein sab se zyada intezaar hai.

---

## Dataset 4: E-commerce Products and Orders

### Dataset Banayein (Synthetic)

```python
import numpy as np
import pandas as pd

np.random.seed(21)
n = 400

category = np.random.choice(["Electronics", "Fashion", "Home", "Beauty", "Books"], n,
                            p=[0.25, 0.3, 0.2, 0.15, 0.1])
base_price = {"Electronics": 300, "Fashion": 60, "Home": 120, "Beauty": 40, "Books": 20}
price = np.round(pd.Series(category).map(base_price).to_numpy() * np.random.uniform(0.6, 1.6, n), 2)
quantity = np.random.randint(1, 5, n)
discount = np.random.choice([0, 5, 10, 20, 30], n)
delivery_days = np.clip(np.round(np.random.normal(4, 1.5, n)), 1, 10).astype(int)
rating = np.clip(np.round(4.6 - delivery_days * 0.15 + np.random.normal(0, 0.6, n)), 1, 5).astype(int)
returned = np.where(rating <= 2, np.random.choice(["Yes", "No"], n, p=[0.5, 0.5]),
                    np.random.choice(["Yes", "No"], n, p=[0.05, 0.95]))

ecom_df = pd.DataFrame({
    "order_id": range(1001, 1001 + n),
    "category": category,
    "price": price,
    "quantity": quantity,
    "discount_percent": discount,
    "payment_method": np.random.choice(["Card", "Cash on Delivery", "Wallet"], n, p=[0.4, 0.4, 0.2]),
    "delivery_days": delivery_days,
    "rating": rating,
    "returned": returned,
})
ecom_df["order_value"] = np.round(ecom_df["price"] * ecom_df["quantity"] * (1 - ecom_df["discount_percent"] / 100), 2)
ecom_df.to_csv("ecommerce_orders.csv", index=False)
print(ecom_df.head())
```

**Explanation:**
- `base_price` → Har category ki aam qeemat; `* uniform(0.6, 1.6)` se variety.
- `delivery_days` → Normal distribution ke aas paas 4 din, 1 se 10 ke darmiyan.
- `rating` → Zyada delivery days = kam rating (noise ke saath).
- `returned` → Kam rating wale orders zyada return hote hain.
- `order_value` = price × quantity × (1 − discount).

**Business questions:**
- Kis category mein orders zyada hain?
- Delivery days aur rating ka kya rishta hai?
- Kaun si payment method sab se zyada use hoti hai?
- Order value ki distribution kaisi hai?
- Return rate kis category mein zyada hai?

**Suitable graphs:** Count plot (category, payment method), box plot (category vs price), scatter/regplot (delivery days vs rating), histogram (order value), heatmap (numeric correlation), bar plot (average rating per category).

**Practice exercise:** `rating` ka count plot banayein. Phir `delivery_days` aur `rating` ka box plot (`x="delivery_days", y="rating"`) banayein aur batayein ke kya zyada delivery days ke saath rating gir rahi hai.

---

## Dataset 5: Weather and Temperature

### Dataset Banayein (Synthetic)

```python
import numpy as np
import pandas as pd

np.random.seed(5)
days = pd.date_range("2025-01-01", "2025-12-31", freq="D")
n = len(days)
day_of_year = days.dayofyear.to_numpy()

def make_city(name, mean_temp, amplitude):
    temp = mean_temp + amplitude * np.sin((day_of_year - 100) * 2 * np.pi / 365) + np.random.normal(0, 1.5, n)
    humidity = np.clip(60 - (temp - mean_temp) * 1.2 + np.random.normal(0, 8, n), 20, 100)
    rainfall = np.where(np.random.rand(n) < 0.12, np.random.exponential(8, n), 0)
    return pd.DataFrame({
        "date": days, "city": name,
        "temperature_c": np.round(temp, 1),
        "humidity_percent": np.round(humidity, 0),
        "rainfall_mm": np.round(rainfall, 1),
    })

weather_df = pd.concat([make_city("Karachi", 27, 6), make_city("Lahore", 24, 11)], ignore_index=True)
weather_df["month"] = weather_df["date"].dt.month
weather_df.to_csv("weather_data.csv", index=False)
print(weather_df.head())
print(weather_df.shape)
```

**Explanation:**
- `np.sin(...)` → Saal bhar mein garmi/sardi ka **seasonal wave** banata hai.
- `make_city(...)` → Ek function jo kisi bhi city ka data banata hai (dobara dobara code likhne se bachaya).
- `humidity` → Temperature se thora ulta, noise ke saath.
- `rainfall` → Sirf 12% dinon mein baarish, baqi dinon mein 0.
- `pd.concat([...])` → Do cities ke tables jore.

**Business questions:**
- Saal bhar mein temperature ka trend kaisa hai?
- Kaun si city zyada garam/thandi hai?
- Kis mahine mein sab se zyada baarish hai?
- Temperature aur humidity ka kya rishta hai?

**Suitable graphs:** Line plot (monthly average temperature per city), box plot (city/month-wise temperature), bar plot (monthly rainfall total), scatter/regplot (temperature vs humidity), histogram (temperature distribution), heatmap (correlation).

**Practice exercise:**
```python
monthly_temp = weather_df.groupby(["month", "city"])["temperature_c"].mean().reset_index()
# sns.lineplot(data=monthly_temp, x="month", y="temperature_c", hue="city", marker="o") banayein.
```
`groupby(["month", "city"])` har (mahina, city) jore ka average temperature nikalta hai. Dekhein kis city mein mausam ka farq (garmi se sardi) zyada hai.

---

# PART 9: Common Errors and Troubleshooting

> **Error se mat ghabrayein.** Programmers ko roz errors aate hain. Sab se zaroori cheez: **error message ki aakhri line parhna.** Wahi batati hai ke masla kya hai.

Har error ke 5 hisse: **(1) Matlab, (2) Wajah, (3) Ghalat code, (4) Sahi code, (5) Aage se bachne ka tareeqa.**

## 9.1 `ModuleNotFoundError`

1. **Matlab:** Python ko woh library mili hi nahi jise aap `import` kar rahe hain.
2. **Wajah:** Library install nahi hai, ya aap kisi aur Python environment mein hain, ya spelling ghalat hai.
3. **Ghalat:**
```text
import seaborn as sns      # ModuleNotFoundError: No module named 'seaborn'
```
4. **Sahi:** Terminal mein:
```bash
pip install seaborn
# ya
python -m pip install seaborn
```
Jupyter ke cell mein: `%pip install seaborn` (phir kernel restart).
5. **Bachao:** Course ke shuru mein sab libraries ek saath install karein (Section 1.11). Library ka naam `scikit-learn` install hota hai lekin `import sklearn` likhte hain; aise farq yaad rakhein.

## 9.2 `FileNotFoundError`

1. **Matlab:** Python ko woh file us jagah mili hi nahi jahan woh dhoondh raha hai.
2. **Wajah:** File ka naam ghalat, ya file dusre folder mein, ya aap ne woh file abhi banayi hi nahi.
3. **Ghalat:**
```text
df = pd.read_csv("student_perfomance.csv")    # spelling ghalat
```
4. **Sahi:**
```python
import os
import pandas as pd

print(os.getcwd())                  # abhi kis folder mein hain?
print(os.listdir())                 # is folder mein kaun si files hain?
df = pd.read_csv("student_performance.csv")
```
5. **Bachao:** CSV aur notebook ko **ek hi folder** mein rakhein. `os.getcwd()` aur `os.listdir()` se check karein. Windows path mein `\` ke bajaye `/` ya `r"C:\path\file.csv"` likhein.

## 9.3 `KeyError`

1. **Matlab:** Aap ne aisa column/key manga jo maujood nahi.
2. **Wajah:** Column ka naam ghalat (spelling, capital letter, space).
3. **Ghalat:**
```text
sns.scatterplot(data=df, x="Study_Hours", y="final_marks")   # KeyError: 'Study_Hours'
```
4. **Sahi:**
```python
import pandas as pd
import seaborn as sns
df = pd.read_csv("student_performance.csv")
print(list(df.columns))       # asal naam dekh lein
sns.scatterplot(data=df, x="study_hours", y="final_marks")
```
5. **Bachao:** Hamesha pehle `print(df.columns)` dekhein. Python **capital aur small letters mein farq** karta hai. Agar column names mein extra space hon to: `df.columns = df.columns.str.strip()`.

## 9.4 `ValueError`

1. **Matlab:** Value ki qism ya shakal ghalat hai (function ko jo cheez mili woh qabil-e-qubool nahi).
2. **Wajah:** Misal: `split=True` ke saath 3 categories, ya `hue` mein ghalat cheez, ya text par numeric kaam.
3. **Ghalat:**
```text
sns.violinplot(data=df, x="class", y="final_marks", hue="class", split=True)   # hue mein 3 categories
```
4. **Sahi:**
```python
import pandas as pd
import seaborn as sns
df = pd.read_csv("student_performance.csv")
sns.violinplot(data=df, x="class", y="final_marks", hue="gender", split=True)   # gender: sirf 2
```
5. **Bachao:** Error message poora parhein; aksar us mein asal wajah likhi hoti hai. Pehle `df["col"].nunique()` se categories ginein.

## 9.5 Ghalat Column Names

1. **Matlab:** `KeyError` ki ek khaas surat.
2. **Wajah:** `df.class` likhna (keyword), `df["Final Marks"]` jab asal naam `final_marks` ho.
3. **Ghalat:**
```text
df.class                      # SyntaxError (class Python ka keyword hai)
df["final marks"]             # KeyError
```
4. **Sahi:**
```python
import pandas as pd
df = pd.read_csv("student_performance.csv")
print(df["class"].head())     # keyword wale naam ke liye square brackets
print(df["final_marks"].head())
```
5. **Bachao:** Column names mein spaces ke bajaye underscore (`_`) rakhein, sab small letters.

## 9.5.1 Strings Ko Numeric Samajh Kar Graph Banana

1. **Matlab:** Number text (string) ban gaya hai, is liye graph/calculation ghalat hai.
2. **Wajah:** CSV mein `"85%"`, `"1,200"`, `"N/A"` jaisi values.
3. **Ghalat:**
```text
df["attendance"] = ["85%", "90%", "N/A"]      # text hai
df["attendance"].mean()                       # error
```
4. **Sahi:**
```python
import pandas as pd

s = pd.Series(["85%", "90%", "N/A"])
s = s.str.replace("%", "", regex=False)       # % hatao
s = pd.to_numeric(s, errors="coerce")         # number banao; N/A -> NaN
print(s)
print(s.mean())
```
5. **Bachao:** Data load karte hi `df.info()` chalayein aur dekhein ke numeric columns numeric hain.

## 9.6 Missing Values Ki Wajah Se Issues

1. **Matlab:** `NaN` values ki wajah se graph ya calculation mein kami/ghalti.
2. **Wajah:** Khali cells, `N/A`, `-`.
3. **Ghalat:** Missing values check kiye bagair graph/statistics.
4. **Sahi:**
```python
import pandas as pd
df = pd.read_csv("student_performance_dirty.csv")      # Section 6.3 se
print(df.isnull().sum())                                # kahan khali hai?
df["attendance"] = df["attendance"].fillna(df["attendance"].median())
# ya khali rows hata dein:
df_small = df.dropna(subset=["attendance"])
```
5. **Bachao:** Har project mein `isnull().sum()` ko pehle 5 steps mein rakhein. Missing values ko bharna ya hatana **sochi samjhi faisla** hona chahiye.

## 9.7 `hue` Column Ka Missing Hona / Ghalat Hona

1. **Matlab:** `hue` mein jo column diya woh data mein nahi, ya `hue` mein bohat zyada categories.
2. **Wajah:** Spelling ya ghalat variable.
3. **Ghalat:**
```text
sns.scatterplot(data=df, x="study_hours", y="final_marks", hue="Pass")   # column ka naam "passed" hai
```
4. **Sahi:**
```python
import pandas as pd
import seaborn as sns
df = pd.read_csv("student_performance.csv")
sns.scatterplot(data=df, x="study_hours", y="final_marks", hue="passed")
```
5. **Bachao:** `df.columns` dekhein. `hue` mein **kam categories (2-5)** wala column dein. `hue="student_name"` jaisa column 40 colors bana kar graph ko ulajha dega.

## 9.8 `plt.show()` Bhool Jana

1. **Matlab:** Graph banta hai lekin screen par nazar nahi aata (khaas tor par `.py` file mein).
2. **Wajah:** `plt.show()` nahi likha.
3. **Ghalat:**
```text
sns.histplot(data=df, x="final_marks")     # script chalayi, koi window nahi khuli
```
4. **Sahi:**
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
df = pd.read_csv("student_performance.csv")
sns.histplot(data=df, x="final_marks")
plt.show()
```
5. **Bachao:** Har graph ke end par `plt.show()` likhein. Jupyter mein bhi aadat rakhein. `savefig` hamesha `show` se **pehle**.

## 9.9 Graph Labels Ka Overlap Hona

1. **Matlab:** X-axis ya title ke labels aapas mein chipak jate hain.
2. **Wajah:** Bohat se categories ya lambe naam.
3. **Ghalat:** Bohat lambi labels wala bar plot bina rotation.
4. **Sahi:**
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
df = pd.read_csv("student_performance.csv")

plt.figure(figsize=(12, 5))                       # chora figure
sns.barplot(data=df, x="student_name", y="final_marks",
            hue="student_name", legend=False, errorbar=None)
plt.xticks(rotation=90)                           # labels ghumao
plt.tight_layout()                                # overlap hataao
plt.show()
```
5. **Bachao:** `figsize` barhayein, `rotation` lagayein, `tight_layout()` lagayein, ya **horizontal bar plot** (`x=numeric, y=category`) banayein.

## 9.10 Pairplot Ka Slow Hona

1. **Matlab:** Pairplot chalne mein bohat der laga ya computer atak gaya.
2. **Wajah:** Bohat zyada columns/rows.
3. **Ghalat:**
```text
sns.pairplot(big_df)      # 40 columns, 100000 rows
```
4. **Sahi:**
```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.read_csv("student_performance.csv")

sample = df.sample(n=30, random_state=42)          # sirf 30 rows
sns.pairplot(sample, vars=["study_hours", "attendance", "final_marks"], corner=True)
plt.show()
```
5. **Bachao:** `vars` se 4-6 columns, `sample()` se data ka hissa, `corner=True`.

## 9.11 Correlation Mein Non-Numeric Columns

1. **Matlab:** `corr()` ko text columns mil gaye.
2. **Wajah:** `df.corr()` poore DataFrame par jab text columns (gender, city) hon.
3. **Ghalat:**
```text
df.corr()            # ValueError: could not convert string to float: 'Ali Raza'
```
4. **Sahi:**
```python
import pandas as pd
df = pd.read_csv("student_performance.csv")

corr = df.corr(numeric_only=True)                       # sirf numeric
# ya
corr2 = df.select_dtypes(include="number").drop(columns="student_id").corr()
print(corr2.round(2))
```
5. **Bachao:** `numeric_only=True` ya `select_dtypes("number")`. `student_id` jaise ID columns hata dein.

## 9.12 Seaborn Version Ke Mutabiq Parameter Errors

1. **Matlab:** Parameter ka naam naye/purane version mein alag hai, is liye error ya warning.
2. **Wajah:** Purana tutorial copy kiya.
3. **Ghalat (purana):**
```text
sns.violinplot(data=df, x="class", y="final_marks", scale="width")   # naye version mein error
sns.distplot(df["final_marks"])                                      # removed/deprecated
```
4. **Sahi:**
```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.read_csv("student_performance.csv")

print(sns.__version__)
sns.violinplot(data=df, x="class", y="final_marks", density_norm="width")
plt.show()
sns.histplot(df["final_marks"], kde=True)
plt.show()
```
5. **Bachao:** `print(sns.__version__)`. Official docs (seaborn.pydata.org) mein apne version ka page dekhein. Section 4.1 ki "purane vs naye" table yaad rakhein.

## 9.13 `palette` Without `hue` Warning

1. **Matlab:** Warning: palette ko hue ke bagair use kiya.
2. **Wajah:** Seaborn 0.13+ mein `palette` tab chalta hai jab `hue` diya ho.
3. **Ghalat:**
```text
sns.barplot(data=df, x="class", y="final_marks", palette="Set2")    # FutureWarning
```
4. **Sahi:**
```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.read_csv("student_performance.csv")

sns.barplot(data=df, x="class", y="final_marks", hue="class", palette="Set2", legend=False)
plt.show()
```
5. **Bachao:** Rang chahiye to `hue` bhi dein (x ke barabar), aur `legend=False` lagayein.

## 9.14 Errors Se Bachne Ke 6 Qaide

1. Pehle `df.head()`, `df.columns`, `df.info()`.
2. Chhota code likh kar chalayein, phir barhayein.
3. Error ki **aakhri line** parhein.
4. Column names copy karke likhein.
5. Library versions check karein.
6. Google ya docs mein error ka text search karein.

---
# PART 10: Final Revision and Teaching Material

## 10.1 Graph Selection Cheat Sheet

> Yeh **shortcuts** hain, **absolute rules nahi**. Har graph ko apne **business question** aur **data type** ke mutabiq chunein.

| Aap kya dekhna chahte hain? | Graph | Seaborn Function |
|---|---|---|
| Waqt ke saath trend | **Line plot** | `sns.lineplot()` |
| Categories ka muqabla (average/sum) | **Bar plot** | `sns.barplot()` |
| Do numerical variables ka relationship | **Scatter plot** | `sns.scatterplot()` |
| Distribution / frequency | **Histogram** | `sns.histplot()` |
| Median, quartiles, potential outliers | **Box plot** | `sns.boxplot()` |
| Category ki tadaad | **Count plot** | `sns.countplot()` |
| Kai numerical features ki correlation | **Heatmap** | `sns.heatmap()` |
| Kai numerical variables ke pairwise relationships | **Pairplot** | `sns.pairplot()` |
| Scatter ke saath fitted trend line | **Regression plot** | `sns.regplot()` / `sns.lmplot()` |
| Distribution ki shakal compare karni ho | **Violin plot** | `sns.violinplot()` |
| Kai graphs ek jagah | **Subplots** | `plt.subplots()` |

**Faisla karne ka tareeqa:**

```
1. Sawal kya hai? (trend / comparison / relationship / distribution / count)
2. Columns ki qism? (numerical / categorical / date)
3. Kitna data hai? (kam data = simple graph)
4. Audience kaun hai? (beginner = simple graph)
```

## 10.2 Graph Comparison Table

| Graph | Variables | Sawal | Kab AVOID karein | Misaal |
|---|---|---|---|---|
| Line | Time + numeric | Trend kaisa? | Order na ho / bohat kam points | Monthly sales |
| Bar | Category + numeric | Kaun zyada/kam? | Bohat categories (50+) | Class-wise average |
| Scatter | Numeric + numeric | Rishta hai? | Categorical data | Study vs marks |
| Histogram | 1 numeric | Phailao kaisa? | Categorical data | Marks distribution |
| Box | Numeric (+ category) | Median/outliers? | Bohat kam data (<10) | Class-wise marks |
| Count | 1 categorical | Kitne har category? | Continuous numeric | Pass/Fail count |
| Heatmap | Matrix (numeric) | Kaun related? | Text columns | Correlation matrix |
| Pairplot | Kai numeric | Sab pairs ka jaiza | Bohat bara data/columns | Pehla EDA |
| Regplot | Numeric + numeric | Trend line? | Non-linear data par seedhi line | Study vs marks |
| Violin | Numeric (+ category) | Shakal compare? | Bohat chhota data | Class-wise distribution |
| Subplots | Kai graphs | Ek page par compare | Bohat zyada graphs (10+) | Dashboard |

## 10.3 Matplotlib vs Seaborn

| Point | Matplotlib | Seaborn |
|---|---|---|
| Import | `import matplotlib.pyplot as plt` | `import seaborn as sns` |
| Banawat | Buniyadi library | Matplotlib ke upar bani |
| Code | Zyada lines | Kam lines |
| DataFrame | Columns khud nikalne parte hain | `data=df, x="col"` seedha |
| Statistical graphs | Khud calculate karein | Ready (box, violin, reg, heatmap) |
| Default look | Saada | Khoobsurat |
| Customization | Bohat zyada control | Matplotlib se customize hota hai |
| Behtar kab | Mukammal custom graphs, subplots layout | Tezi se EDA graphs |

**Misaal (same graph, do tareeqe):**

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("student_performance.csv")

# Matplotlib se
plt.figure(figsize=(6, 4))
plt.scatter(df["study_hours"], df["final_marks"])
plt.xlabel("Study Hours")
plt.ylabel("Final Marks")
plt.title("Matplotlib Scatter")
plt.show()

# Seaborn se
plt.figure(figsize=(6, 4))
sns.scatterplot(data=df, x="study_hours", y="final_marks", hue="passed")
plt.title("Seaborn Scatter")
plt.show()
```
- Matplotlib mein `plt.scatter(x_values, y_values)` do Series deta hai.
- Seaborn mein `data=df` aur column ke **naam** dete hain, aur `hue` se extra group aasaan hai.
- Dono mein title/labels `plt` se lagte hain, kyun ke Seaborn Matplotlib par bana hai.

## 10.4 EDA Checklist

- [ ] Business sawal likha hua hai.
- [ ] Data load ho gaya (`read_csv`).
- [ ] `shape`, `head()`, `tail()` dekhe.
- [ ] `info()` se data types check kiye.
- [ ] `isnull().sum()` se missing values dekhi.
- [ ] `duplicated().sum()` se duplicates dekhe.
- [ ] Invalid values (negative, 100 se zyada) check kiye.
- [ ] Numerical aur categorical columns alag kiye.
- [ ] `describe()` se summary dekhi.
- [ ] Har important column ki distribution dekhi (histogram/box).
- [ ] Categories ki counts dekhi (countplot/value_counts).
- [ ] Do columns ka rishta dekha (scatter/bar/box).
- [ ] Correlation heatmap dekhi (sirf numeric columns).
- [ ] Outliers investigate kiye (delete karne se pehle wajah).
- [ ] Har graph ka title, labels, units theek hain.
- [ ] Insights data se likhe (guess se nahi).
- [ ] Limitations likhi.
- [ ] Cleaned data aur report save ki.

## 10.5 Important Functions Revision

| Function | Kaam |
|---|---|
| `pd.read_csv()` | CSV load karna |
| `df.head()`, `df.tail()` | Pehli/aakhri rows |
| `df.shape` | (rows, columns) |
| `df.info()` | Types aur non-null |
| `df.describe()` | Statistical summary |
| `df.isnull().sum()` | Missing values |
| `df.duplicated().sum()` | Duplicates |
| `df.drop_duplicates()` | Duplicates hatana |
| `df.fillna()`, `df.dropna()` | Missing bharna/hatana |
| `df["col"].value_counts()` | Category counts |
| `df.groupby("a")["b"].mean()` | Group-wise average |
| `df.corr(numeric_only=True)` | Correlation matrix |
| `df.select_dtypes("number")` | Numeric columns chunna |
| `df.melt()` | Wide ko long banana |
| `pd.crosstab()` | Do categories ki cross table |
| `sns.set_theme()` | Style |
| `sns.lineplot/barplot/scatterplot/histplot/boxplot/countplot/heatmap/pairplot/regplot/violinplot` | 10 graphs |
| `plt.figure(figsize=)` | Size |
| `plt.title/xlabel/ylabel` | Text |
| `plt.subplots()` | Multiple graphs |
| `plt.tight_layout()` | Overlap hatana |
| `plt.savefig()` | Image save |
| `plt.show()` | Graph dikhana |

---

## 10.6 30 MCQs (Answers Ke Saath)

**Q1.** EDA ka matlab?
A) Easy Data Analysis B) Exploratory Data Analysis C) Extra Data Algorithm D) Estimated Data Average
**Answer: B**

**Q2.** DataFrame kya hai?
A) Ek graph B) Ek table (rows/columns) C) Ek file D) Ek library
**Answer: B**

**Q3.** Series kya hai?
A) Poora table B) Ek column ya row C) Ek graph D) Ek error
**Answer: B**

**Q4.** `sns` kis library ka chhota naam hai?
A) scikit B) seaborn C) scipy D) sklearn
**Answer: B**

**Q5.** `df.shape` kya batata hai?
A) Data ki shakal ka graph B) (rows, columns) C) Missing values D) Data types
**Answer: B**

**Q6.** Missing values kaise check karte hain?
A) `df.shape` B) `df.isnull().sum()` C) `df.head()` D) `df.plot()`
**Answer: B**

**Q7.** Trend dekhne ke liye sab se munasib graph?
A) Pie B) Line plot C) Count plot D) Heatmap
**Answer: B**

**Q8.** Categories ki tadaad dikhane wala graph?
A) Scatter B) Count plot C) Line D) Regplot
**Answer: B**

**Q9.** Do numerical variables ka relationship?
A) Scatter plot B) Count plot C) Bar plot D) Subplot
**Answer: A**

**Q10.** Histogram mein Y-axis aam tor par kya hoti hai?
A) Average B) Frequency/Count C) Correlation D) Median
**Answer: B**

**Q11.** Box plot ke andar ki line kya hai?
A) Mean B) Mode C) Median D) Maximum
**Answer: C**

**Q12.** IQR ka formula?
A) Q1 − Q3 B) Q3 − Q1 C) Q1 + Q3 D) Max − Min
**Answer: B**

**Q13.** Heatmap mein correlation ki range?
A) 0 se 100 B) -1 se +1 C) 0 se 1 D) -100 se 100
**Answer: B**

**Q14.** Correlation matrix ke diagonal par kya hota hai?
A) 0 B) 1 C) -1 D) Random
**Answer: B**

**Q15.** `annot=True` kya karta hai?
A) Rang badalta B) Cells mein numbers dikhata C) Graph save karta D) Mask lagata
**Answer: B**

**Q16.** Pairplot mein diagonal par kya hota hai?
A) Heatmap B) Histogram/KDE C) Pie D) Line
**Answer: B**

**Q17.** `corner=True` ka faida?
A) Rang B) Sirf aadha (neeche ka) grid C) Zyada size D) Save
**Answer: B**

**Q18.** Regression line kya dikhati hai?
A) Har student ka exact marks B) Overall trend C) Missing data D) Categories
**Answer: B**

**Q19.** `lmplot` aur `regplot` mein farq?
A) Koi nahi B) lmplot figure-level hai (hue/col/row support) C) regplot sirf bar ke liye D) lmplot chhota hai
**Answer: B**

**Q20.** Violin plot ki width kya batati hai?
A) Mean B) Data ki density C) Missing values D) Outliers sirf
**Answer: B**

**Q21.** Violin plot mein `split=True` kab chalta hai?
A) Hamesha B) `hue` mein exactly 2 categories ho C) 3 categories D) kabhi nahi
**Answer: B**

**Q22.** `plt.subplots(2, 3)` kitne graphs banayega?
A) 5 B) 6 C) 8 D) 23
**Answer: B**

**Q23.** Subplots mein title kaise lagate hain?
A) `plt.title` hamesha B) `axes[i].set_title()` C) `print` D) `df.title`
**Answer: B**

**Q24.** Correlation ka matlab?
A) Cause B) Do cheezon ka saath saath badalna C) Average D) Outlier
**Answer: B**

**Q25.** Outlier ka sahi tareeqa?
A) Foran delete B) Pehle wajah investigate karein C) Ignore D) Sab ko average se badlein
**Answer: B**

**Q26.** Naye Seaborn (0.13+) mein violin ke liye normalization ka parameter?
A) `scale` B) `density_norm` C) `normalize` D) `width_norm`
**Answer: B**

**Q27.** `errorbar=None` kya karta hai?
A) Error dikhata B) Error bar/band nahi dikhata C) Data hata deta D) Graph band
**Answer: B**

**Q28.** Count plot mein `x` aur `y` dono dena?
A) Zaroori B) Sirf ek dena hota hai C) Dono ulta D) Error nahi
**Answer: B**

**Q29.** Data ko CSV mein save karne ka function?
A) `df.save()` B) `df.to_csv()` C) `df.write()` D) `df.export()`
**Answer: B**

**Q30.** Synthetic data kya hota hai?
A) Real hospital data B) Code se banaya hua practice data C) Chori ka data D) Purana data
**Answer: B**

---

## 10.7 15 Practical Coding Questions

> Sab `student_performance.csv` par hain jab tak kuch aur na likha ho.

1. `df.shape`, `df.info()` aur `df.describe()` print karein aur 3 baatein likhein jo aap ne seekhi.
2. Teeno subjects ka average ek bar plot mein dikhayein (hint: `melt`).
3. `study_hours` vs `math_marks` ka scatter plot banayein, `hue="gender"` ke saath.
4. `attendance` ka histogram `bins=6`, `bins=12` ke saath banayein; farq likhein.
5. `final_marks` ka class-wise box plot banayein aur median sab se zyada wali class batayein.
6. `city` ka count plot, bars ko zyada se kam tarteeb mein.
7. Numeric columns ki correlation heatmap (sirf neeche ka triangle) banayein; sab se strong aur sab se weak pair batayein.
8. `vars=["study_hours","attendance","final_marks"]` ke saath pairplot, `hue="gender"`.
9. `attendance` vs `final_marks` ka regplot banayein aur slope `np.polyfit` se print karein.
10. `gender` ke mutabiq `final_marks` ka violin plot (`cut=0`) banayein.
11. 2×2 subplots: histogram (final_marks), scatter (study vs final), box (class vs final), count (passed).
12. `monthly_performance.csv` mein sirf Class 10 ka line plot banayein (filter karke).
13. IQR rule se `math_marks` mein outliers dhoondhein.
14. Ek naya column `grade` banayein: `final_marks >= 80` → A, `>= 60` → B, `>= 40` → C, warna F; phir grade ka count plot banayein. (hint: `pd.cut`)
15. `sales_data.csv` se monthly total sales ka line plot banayein (Dataset 2).

**Question 14 ka hint:**

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

df = pd.read_csv("student_performance.csv")
df["grade"] = pd.cut(df["final_marks"], bins=[0, 40, 60, 80, 100],
                     labels=["F", "C", "B", "A"], right=False)
sns.countplot(data=df, x="grade", order=["A", "B", "C", "F"])
plt.title("Grade Distribution")
plt.show()
```
- `pd.cut(values, bins, labels)` numbers ko ranges (groups) mein baant kar naam deta hai.
- `bins=[0, 40, 60, 80, 100]` → 0-40, 40-60, 60-80, 80-100 (dhyan dein: 100 marks wala student alag range se bahar ja sakta hai; is dataset mein max 87.7 hai, is liye theek hai).
- `right=False` → Left side shamil, right side shamil nahi: `[0,40)`, `[40,60)`, ...

---

## 10.8 5 Mini Projects

1. **Class Result Analyzer:** `student_performance.csv` se pass percentage, topper (`idxmax`), class-wise average aur 3 graphs.
2. **Sales Dashboard:** `sales_data.csv` se monthly line plot, region bar plot, product box plot, marketing vs sales regplot, 2×2 dashboard.
3. **Hospital Waiting Time Study:** `hospital_visits.csv` se wait time histogram, department box plot, wait vs satisfaction regplot; 3 insights likhein.
4. **E-commerce Return Analysis:** `ecommerce_orders.csv` se category-wise return percentage, delivery days vs rating, order value distribution.
5. **City Weather Comparison:** `weather_data.csv` se monthly temperature line plot (do cities), rainfall bar plot, temperature vs humidity scatter.

Har mini project mein: **problem statement, data checks, kam az kam 3 graphs, 3 insights, 2 limitations.**

## 10.9 Final Capstone Project

**Title:** *End-to-End EDA on a Dataset of Your Choice*

**Requirements:**
1. Kisi bhi ek dataset (apna ya Kaggle/UCI jaisi site se, **license check karke**) ko chunein; ya Part 8 ke synthetic datasets mein se ek.
2. **Business problem** 5 sawalon mein likhein.
3. 16-step EDA workflow follow karein.
4. Kam az kam **8 alag graphs** (har graph ki wajah likhein).
5. Ek **subplots dashboard** (2×3) save karein (`savefig`).
6. Cleaned data `*_clean.csv` mein save karein.
7. `eda_report.md` (insights, conclusion, limitations, next steps).
8. 5 minute ki presentation.

**Marking Guide (100 marks):**

| Hissa | Marks |
|---|---|
| Problem statement | 10 |
| Data inspection aur cleaning | 20 |
| Graphs ki sahi selection aur code | 25 |
| Labels/titles/readability | 10 |
| Insights (data se supported) | 20 |
| Limitations aur next steps | 10 |
| Presentation | 5 |

## 10.10 Teacher Ke Liye Simple Teaching Sequence

| Din | Topic | Activity |
|---|---|---|
| 1 | Data Visualization/EDA introduction, installation | Setup check, version print |
| 2 | Pandas basics, dataset creation, data inspection | `head/info/describe` practice |
| 3 | Line plot, Bar plot | Monthly aur class-wise graphs |
| 4 | Scatter plot, Correlation vs causation | Class mein "Ice-cream aur doobna" misaal |
| 5 | Histogram, Distribution, Skewness | Marks ka histogram, bins ke saath khelna |
| 6 | Box plot (quartiles zero se) | Haath se Q1, Q2, Q3 nikalna |
| 7 | Count plot, Heatmap | Pass/Fail aur correlation |
| 8 | Pairplot, Regression plot | Sensible columns chunne ki mashq |
| 9 | Violin plot, Subplots | Mini dashboard |
| 10 | Customization, Troubleshooting | Intentional errors theek karwana |
| 11 | EDA workflow, Dirty data cleaning | Dirty dataset clean karwana |
| 12 | Real project | Student Performance Analysis |
| 13 | Practice datasets | Group mein mini projects |
| 14 | Revision, MCQs, Viva | Quiz |
| 15 | Capstone presentations | Marking |

**Teaching tips:**
- Har chapter pehle **real-life example** se shuru karein, phir code.
- Students se code **khud type** karwayein.
- **Har graph ke baad** poochein: "Is graph se aap kya samjhe?"
- Intentional errors dikha kar troubleshooting sikhayein.
- Hamesha dohrayein: **Correlation ≠ Causation.**
- Synthetic aur real data ka farq har dafa clear karein.

## 10.11 Students Ke Liye Homework

| Hafta | Homework |
|---|---|
| 1 | Python/pandas basics, dataset load, `head/info/describe` |
| 2 | Line, bar, scatter plot (apne data par) |
| 3 | Histogram, box, count plot |
| 4 | Heatmap, pairplot, regplot, violin |
| 5 | Subplots dashboard + customization |
| 6 | Mini project (koi ek) |
| 7 | Capstone project |

**Roz ka mashq:** Har roz **ek graph khud banayein** aur uske neeche **do line ka nateeja** likhein.

## 10.12 Viva Questions (Simple Jawab Ke Saath)

1. **EDA kya hai?** Model banane se pehle data ko check karna aur samajhna.
2. **Seaborn aur Matplotlib mein farq?** Matplotlib buniyadi hai; Seaborn us ke upar bana hai aur kam code mein statistical graphs deta hai.
3. **Histogram aur bar plot mein farq?** Histogram numeric data ko ranges mein baanta hai (distribution), bar plot categories compare karta hai.
4. **Median kya hai?** Tarteeb se lagaye gaye data ki beech wali value.
5. **IQR kya hai?** Q3 − Q1, yani beech ke 50% data ka phailao.
6. **Outlier kya hai?** Baqi data se bohat alag value; har outlier ghalti nahi hota.
7. **Correlation kya hai?** Do variables ka saath saath badalna (range -1 se +1).
8. **Correlation aur causation mein farq?** Correlation sirf rishta batata hai, causation matlab ek cheez doosri ki wajah hai.
9. **Heatmap ke diagonal par 1 kyun hota hai?** Kyun ke har variable apne aap se mukammal correlated hota hai.
10. **Pairplot slow kyun hota hai?** Kyun ke columns ki tadaad ke square jitne graphs bante hain.
11. **KDE kya hai?** Histogram ka smooth (naram) version, density curve.
12. **Violin plot kab use karte hain?** Jab distribution ki shakal compare karni ho (zyada data hone par).
13. **Overfitting kya hai?** Model ka training data ko bohat zyada yaad kar lena aur naye data par kharab chalna.
14. **Subplot kya hai?** Ek figure mein kai chhote graphs.
15. **Missing values ko kaise handle karte hain?** Pehle check karein, phir wajah soch kar bharein (mean/median) ya hatayein.
16. **Synthetic data kyun use kiya?** Practice ke liye; yeh asal records nahi hain, aur is ke nateeje real duniya par seedhe laagu nahi hote.

---

# Khatma: Course Ka Final Quality Checklist

Course mukammal karne ke baad is checklist se verify karein:

- [x] Har graph zero se explain kiya gaya (kya, kyun, kab, example).
- [x] Har graph ka purpose aur real-life use clear hai.
- [x] Required aur optional parameters alag batayein gaye (Part 4).
- [x] Code **Seaborn 0.13+** ke mutabiq (modern syntax: `errorbar`, `density_norm`, `hue` + `legend=False`, `g.figure`).
- [x] Code examples ko Python 3.12, pandas 3.0, NumPy 2.4, Matplotlib 3.10, Seaborn 0.13 par chala kar test kiya gaya (sirf `robust`/`lowess` ke liye `statsmodels` alag se chahiye).
- [x] Code ki har meaningful line explain ki gayi.
- [x] Output interpretation har chapter mein hai.
- [x] Common mistakes aur sahi code (Part 9).
- [x] Column names consistent (`study_hours`, `final_marks`, `passed`, ...).
- [x] Project ke conclusions actual data ke numbers se supported hain.
- [x] Synthetic data har jagah clearly label kiya gaya.

> **Aakhri nasihat:** Graphs banana sirf code nahi, **sawal poochna aur jawab dhoondhna** hai. Pehle sawal, phir sahi graph, phir insight. Mubarak ho, ab aap data visualization aur EDA ke liye tayyar hain! 🎉

---

*Yeh course Roman Urdu mein beginners ke liye tayyar kiya gaya hai. Saare datasets synthetic practice data hain, asal records nahi.*
