# 💻 ThinkPad Hackintosh Battery Limit (Simple Fix)

## ❗ Problem
Hackintosh (macOS) does not support battery charge limits.

→ battery stays at 100%  
→ faster battery wear  

(confirmed by many users – apps often don't work properly on Hackintosh)

---

## 💡 Solution
Use Linux once to set battery limits directly in hardware.

No Windows  
No extra apps  

---

## 🔧 Steps

### 1. Boot Linux (Mint recommended)

Use live USB (no install needed)

---

### 2. Run in terminal:

echo 60 | sudo tee /sys/class/power_supply/BAT0/charge_control_start_threshold  
echo 80 | sudo tee /sys/class/power_supply/BAT0/charge_control_end_threshold  

echo 60 | sudo tee /sys/class/power_supply/BAT0/charge_start_threshold  
echo 80 | sudo tee /sys/class/power_supply/BAT0/charge_stop_threshold  

---

### 3. Reboot back to macOS

---

## ✅ Result

Battery will:

- start charging at ~60%  
- stop charging at ~80%  

→ better battery lifespan  

---

## ⚠️ Important

- macOS may show wrong charging status  
- trust real behavior, not the icon  

---

## 💡 Practical tip

If battery goes above 80%:

→ just unplug charger shortly before 80%  
→ done 😄  

---

## 🧠 Why this works

Linux writes values directly to laptop hardware (EC).

These settings persist after reboot.

macOS doesn't control it —  
but still follows it.

---

## 🧪 Tested on

- ThinkPad T430  
- macOS Monterey  
- OpenCore  

---

## 🙌 Credits

Dušan (real-world solution)
