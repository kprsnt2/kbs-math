# The KBS Calendar Method (Kadasi Bhoomaiah System) 📐

> **Invented by Sri Kadasi Bhoomaiah:**  
> Retired **Mandal Educational Officer (MEO)** in 2013. Sri Bhoomaiah served passionately as a Mathematics Teacher and School Assistant from the start of his career, and dedicated his final 10 years of service as MEO leading schools and teachers. He recently invented and formulated this ingenious mental math calendar method to empower students, educators, and mathematics enthusiasts worldwide.

---

## 🌟 Overview & Mathematical Verification

Sri Kadasi Bhoomaiah's formula for finding the day of the week for any calendar date in history is **mathematically sound, exceptionally elegant, and 100.0000% accurate**.

We performed an exhaustive test on **292,194 consecutive days across 800 years (from 1600 to 2399)** against official astronomical calendar standards:
- **Total Days Tested:** 292,194
- **Mismatches / Errors:** 0
- **Accuracy Rate:** **100.0000%**

---

## 🧠 The KBS Formula Explained

For any date with **Day $D$**, **Month $M$**, and **Year $Y$** (with last 2 digits $YY = Y \bmod 100$):

$$\text{Total Sum} = (YY \bmod 7) + \left\lfloor\frac{YY}{4}\right\rfloor + D + \text{MonthCode} + \text{CenturyCode} - \text{LeapAdjustment}$$

$$\text{Day of the Week} = \text{Total Sum} \bmod 7$$

### 1. Day of Week Mapping
| Remainder (mod 7) | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Day** | **Sunday** | **Monday** | **Tuesday** | **Wednesday** | **Thursday** | **Friday** | **Saturday** |

---

### 2. Sri Kadasi Bhoomaiah's Month Value Codes
| Month | Code | Why It Works / Memory Trick |
| :--- | :---: | :--- |
| **January** | **0** | Year begins with 0; pairs with October |
| **February** | **3** | $0 + 31\text{ days of Jan} \equiv 3 \pmod 7$ |
| **March** | **3** | Feb has 28 days $\equiv 0 \pmod 7$, so March remains 3 |
| **April** | **6** | $3 + 31\text{ days of Mar} \equiv 6 \pmod 7$ |
| **May** | **1** | May Day is 1st of May! ($6 + 30 \equiv 1 \pmod 7$) |
| **June** | **4** | "JUNE" has 4 letters ($1 + 31 \equiv 4 \pmod 7$) |
| **July** | **6** | Pairs with April ($4 + 30 \equiv 6 \pmod 7$) |
| **August** | **2** | "Au-gust" has 2 syllables ($6 + 31 \equiv 2 \pmod 7$) |
| **September** | **5** | Pairs with December ($2 + 31 \equiv 5 \pmod 7$) |
| **October** | **0** | "O" looks like 0 ($5 + 30 \equiv 0 \pmod 7$) |
| **November** | **3** | Triad with Feb & Mar ($0 + 31 \equiv 3 \pmod 7$) |
| **December** | **5** | Pairs with September ($3 + 30 \equiv 5 \pmod 7$) |

**Grouped for student recitation:**
- **0:** Jan, Oct
- **1:** May
- **2:** Aug
- **3:** Feb, Mar, Nov
- **4:** Jun
- **5:** Sep, Dec
- **6:** Apr, Jul

---

### 3. Century Offsets & The "Minus 1" Rule

Sri Kadasi Bhoomaiah calibrated his base formula for the **1900s (1900–1999)**, where **Century Offset = 0**.

Because of the 400-year Gregorian cycle:
- **1900 – 1999:** Century Offset = **0** *(The KBS Base Formula)*
- **2000 – 2099:** Century Offset = **-1** *(or +6)* $\to$ **Sri Bhoomaiah's "Minus 1 Rule"!**
- **1800 – 1899:** Century Offset = **+2** *(or -5)*
- **1700 – 1799:** Century Offset = **+4** *(or -3)*
- **1600 – 1699:** Century Offset = **+6** *(or -1)*

The 400-year perpetual cycle is: **6, 4, 2, 0** (or **-1, -3, -5, 0**).

For any century $C = \lfloor \text{Year} / 100 \rfloor$:
$$\text{Century Code} = (2 \times (3 - (C \bmod 4))) \bmod 7$$

---

### 4. Leap Year Adjustment (Jan & Feb)

A year is a leap year if:
$$(Y \bmod 4 == 0 \text{ and } Y \bmod 100 \ne 0) \quad\text{OR}\quad (Y \bmod 400 == 0)$$

- **Why subtract 1 for Jan & Feb?**
  The term $\lfloor YY / 4 \rfloor$ counts leap days assuming the extra leap day has occurred. However, the leap day is **February 29**. For dates in **January** and early **February**, that extra day hasn't arrived yet.
  Therefore, for leap years in January and February, we **subtract 1**.

---

## 📱 Web Application Features

The included web app (`index.html`, `styles.css`, `app.js`) is completely self-contained with **zero external dependencies**:
1. **Interactive Calculator:** Select any day, month, and year, or click historical presets (Independence Day 1947, Republic Day 1950, Gandhi Jayanti 1869, Y2K Millennium 2000, etc.).
2. **KBS Step-by-Step Breakdown:** Visual cards detailing each of Sri Bhoomaiah's 7 mental math steps.
3. **5-Second Mental Math Secret:** Explains how to cast out multiples of 7 on the fly to do everything mentally in seconds.
4. **KBS Classroom Quiz & Practice:** Random date challenge with scoring, streaks, and teacher hints to help students learn mental math.
5. **Memory Cheat Sheets:** Visual tables and grouping mnemonics for month codes and century offsets.
6. **Live In-Browser Verification Engine:** Runs directly in the user's browser, verifying up to 800 years (292,194 days) with a live progress bar.
7. **Educational Explanation:** Clear guide to the modular arithmetic principles for high schoolers.
8. **Printable Handout Mode:** Clean `@media print` layout for school teachers to print classroom study sheets.
9. **WhatsApp & Clipboard Sharing:** Share breakdowns directly with friends and students.
10. **Dark / Light Theme:** Accessible and easy on the eyes.

---

## 🚀 How to Host This Web App (Free & Easy)

You can host and share this app in under 2 minutes using any of the following free services:

### Method 1: GitHub Pages (Recommended — Free Forever)
1. Create a free account at [GitHub.com](https://github.com).
2. Create a new repository (e.g. `kbs-calendar-method`).
3. Upload the files: `index.html`, `styles.css`, `app.js`, and `README.md`.
4. Go to **Settings** &rarr; **Pages**.
5. Under "Branch", select `main` (or `master`) and click **Save**.
6. GitHub will give you a public URL (e.g. `https://yourusername.github.io/kbs-calendar-method`) that anyone can open on their mobile phone or PC!

### Method 2: Netlify Drop (Instant in 10 Seconds — No Setup)
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop).
2. Drag and drop this `maths` folder directly into your browser.
3. Netlify immediately publishes it and gives you a free shareable link.

### Method 3: Vercel
1. Install Vercel CLI (`npx vercel`) or connect your GitHub repository at [vercel.com](https://vercel.com).
2. Deploy with zero configuration.

### Method 4: Offline / Direct File (Works Anywhere!)
- You don't even need an internet connection! Simply double-click `index.html` on any laptop, tablet, or smartphone to run the entire app offline anywhere in the world.
