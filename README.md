<!-- Header Banner -->
<div align="center">

```
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Suriya Prakash - Header</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@900&family=Rajdhani:wght@700&display=swap');

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: #000;
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    overflow: hidden;
    font-family: 'Orbitron', monospace;
  }

  .container {
    position: relative;
    text-align: center;
    z-index: 10;
    padding: 40px;
  }

  /* Disco ball sparks */
  .spark {
    position: fixed;
    width: 4px;
    height: 4px;
    border-radius: 50%;
    animation: sparkFly linear infinite;
    pointer-events: none;
  }

  @keyframes sparkFly {
    0%   { transform: translate(0, 0) scale(1); opacity: 1; }
    100% { transform: translate(var(--dx), var(--dy)) scale(0); opacity: 0; }
  }

  /* Main title */
  .name-suriya {
    font-size: clamp(60px, 12vw, 130px);
    font-weight: 900;
    letter-spacing: 0.12em;
    line-height: 1;
    background: linear-gradient(90deg,
      #ff0080, #ff4500, #ffd700, #00ff88, #00cfff, #bf00ff, #ff0080
    );
    background-size: 300% 100%;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: discoShift 1.5s linear infinite, glowPulse 2s ease-in-out infinite;
    position: relative;
    text-shadow: none;
    filter: drop-shadow(0 0 20px rgba(255,255,255,0.3));
  }

  .name-prakash {
    font-size: clamp(30px, 6vw, 70px);
    font-weight: 900;
    letter-spacing: 0.3em;
    background: linear-gradient(90deg,
      #00cfff, #bf00ff, #ff0080, #ffd700, #00ff88, #00cfff
    );
    background-size: 300% 100%;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    animation: discoShift 1.5s linear infinite reverse, glowPulse 2s ease-in-out infinite 0.5s;
    filter: drop-shadow(0 0 15px rgba(255,255,255,0.2));
    margin-top: 8px;
  }

  @keyframes discoShift {
    0%   { background-position: 0% 50%; }
    100% { background-position: 300% 50%; }
  }

  @keyframes glowPulse {
    0%, 100% { filter: drop-shadow(0 0 20px #ff0080) drop-shadow(0 0 40px #ff008066); }
    25%       { filter: drop-shadow(0 0 20px #ffd700) drop-shadow(0 0 40px #ffd70066); }
    50%       { filter: drop-shadow(0 0 20px #00cfff) drop-shadow(0 0 40px #00cfff66); }
    75%       { filter: drop-shadow(0 0 20px #00ff88) drop-shadow(0 0 40px #00ff8866); }
  }

  /* Subtitle */
  .subtitle {
    font-family: 'Rajdhani', sans-serif;
    font-size: clamp(13px, 2.5vw, 20px);
    letter-spacing: 0.4em;
    color: #aaa;
    margin-top: 18px;
    animation: fadeFlicker 3s ease-in-out infinite;
  }

  @keyframes fadeFlicker {
    0%, 100% { opacity: 0.7; }
    50% { opacity: 1; color: #fff; }
  }

  /* Scanline overlay */
  .scanlines {
    position: fixed;
    inset: 0;
    background: repeating-linear-gradient(
      to bottom,
      transparent 0px,
      transparent 3px,
      rgba(0,0,0,0.15) 3px,
      rgba(0,0,0,0.15) 4px
    );
    pointer-events: none;
    z-index: 5;
  }

  /* Disco light beams */
  .beam {
    position: fixed;
    width: 2px;
    height: 60vh;
    top: 0;
    transform-origin: top center;
    animation: beamSweep var(--dur) ease-in-out infinite alternate;
    opacity: 0.15;
    pointer-events: none;
    z-index: 1;
  }

  @keyframes beamSweep {
    0%   { transform: rotate(var(--start)); }
    100% { transform: rotate(var(--end)); }
  }

  /* Corner decorations */
  .corner {
    position: fixed;
    width: 60px; height: 60px;
    border-color: #333;
    border-style: solid;
    animation: cornerPulse 2s ease-in-out infinite;
  }
  .corner.tl { top: 20px; left: 20px; border-width: 2px 0 0 2px; }
  .corner.tr { top: 20px; right: 20px; border-width: 2px 2px 0 0; }
  .corner.bl { bottom: 20px; left: 20px; border-width: 0 0 2px 2px; }
  .corner.br { bottom: 20px; right: 20px; border-width: 0 2px 2px 0; }

  @keyframes cornerPulse {
    0%, 100% { border-color: #333; }
    50% { border-color: #00cfff44; }
  }

  /* Divider line */
  .divider {
    width: 200px;
    height: 2px;
    background: linear-gradient(90deg, transparent, #00cfff, #ff0080, transparent);
    margin: 16px auto 0;
    animation: dividerShift 2s linear infinite;
    background-size: 200% 100%;
  }
  @keyframes dividerShift {
    0%   { background-position: 0% 50%; }
    100% { background-position: 200% 50%; }
  }
</style>
</head>
<body>

<div class="scanlines"></div>
<div class="corner tl"></div>
<div class="corner tr"></div>
<div class="corner bl"></div>
<div class="corner br"></div>

<div class="container">
  <div class="name-suriya">SURIYA</div>
  <div class="name-prakash">P R A K A S H</div>
  <div class="divider"></div>
  <div class="subtitle">CYBERSECURITY RESEARCHER &nbsp;|&nbsp; BUG HUNTER</div>
</div>

<script>
  // Disco beams
  const beamColors = ['#ff0080','#ffd700','#00cfff','#00ff88','#bf00ff','#ff4500'];
  const positions = [15, 25, 35, 50, 65, 75, 85];
  positions.forEach((pos, i) => {
    const beam = document.createElement('div');
    beam.className = 'beam';
    beam.style.left = pos + '%';
    beam.style.background = beamColors[i % beamColors.length];
    beam.style.setProperty('--dur', (2 + Math.random() * 2) + 's');
    beam.style.setProperty('--start', (-30 + Math.random() * 10) + 'deg');
    beam.style.setProperty('--end',   (10 + Math.random() * 30) + 'deg');
    document.body.appendChild(beam);
  });

  // Continuous sparks
  function createSpark() {
    const spark = document.createElement('div');
    spark.className = 'spark';
    const x = Math.random() * window.innerWidth;
    const y = Math.random() * window.innerHeight;
    const angle = Math.random() * 360;
    const dist = 60 + Math.random() * 120;
    const dx = Math.cos(angle * Math.PI / 180) * dist;
    const dy = Math.sin(angle * Math.PI / 180) * dist;
    const colors = ['#ff0080','#ffd700','#00cfff','#00ff88','#bf00ff','#ffffff','#ff4500'];
    spark.style.cssText = `
      left:${x}px; top:${y}px;
      background:${colors[Math.floor(Math.random()*colors.length)]};
      --dx:${dx}px; --dy:${dy}px;
      animation-duration:${0.6 + Math.random() * 1}s;
      animation-delay:${Math.random() * 0.5}s;
      box-shadow: 0 0 4px currentColor;
    `;
    document.body.appendChild(spark);
    setTimeout(() => spark.remove(), 1600);
  }

  setInterval(createSpark, 40);
</script>
</body>
</html>

```

# 👾 Suriya Prakash Sekar
### `[ IT Engineer | Cybersecurity Researcher | Bug Hunter | Penetration Tester ]`

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=18&pause=1000&color=00FF41&center=true&vCenter=true&width=500&lines=Hunting+Bugs+%F0%9F%90%9B+|+Breaking+Things+Ethically;Penetration+Tester+%7C+Web+Security;Network+%26+Firewall+Specialist;Linux+%26+Windows+Security+Expert)](https://git.io/typing-svg)

![Profile Views](https://komarev.com/ghpvc/?username=Suryaping01&color=00ff41&style=flat-square&label=PROFILE+VIEWS)
[![GitHub followers](https://img.shields.io/github/followers/Suryaping01?label=Followers&style=flat-square&color=00ff41)](https://github.com/Suryaping01)

</div>

---

## 🕵️ About Me

```bash
┌──(suriya㉿kali)-[~]
└─$ whoami
```

```
> Name      : Suriya Prakash Sekar
> Role      : Cybersecurity Researcher & Bug Hunter
> Level     : Intermediate
> Status    : Always Learning | Always Hunting 🎯
> OS        : Kali Linux / Windows
> Motto     : "Think like an attacker, defend like a pro."
```

---

## 📝 About Me

I'm **Suriya Prakash Sekar**, a passionate **Cybersecurity Researcher** and **Bug Bounty Hunter** with a deep interest in identifying and responsibly disclosing vulnerabilities across web applications and network infrastructures.

My journey into cybersecurity started with a curiosity for how systems work — and more importantly, how they can be broken. That curiosity evolved into a professional pursuit of **ethical hacking**, **penetration testing**, and **bug bounty programs** on platforms like HackerOne and Bugcrowd.

I specialize in **Web Application Security**, uncovering vulnerabilities such as XSS, SQLi, IDOR, SSRF, and broken authentication. My experience also extends to **Network Security** and **Firewall configuration**, working across both **Windows** and **Linux** environments with a security-first mindset.

Currently, I'm sharpening my skills through hands-on labs, CTF challenges, and real-world bug bounty programs — with a long-term goal of achieving the **OSCP certification** and becoming a professional penetration tester.

> 💡 *I believe security is not just a skill — it's a responsibility. Every bug I find makes the internet a safer place.*

---

## 🎯 Focus Areas

<div align="center">

| 🔍 Domain | 🛠️ Skill Level |
|-----------|----------------|
| 🐛 Bug Bounty Hunting | ██████████ Intermediate |
| 🔓 Penetration Testing | ██████████ Intermediate |
| 🌐 Web Application Security | ██████████ Intermediate |
| 🔥 Firewall & Network Security | ████████████ Intermediate |
| 🐧 Linux Security | ████████░░ Intermediate |
| 🪟 Windows Platform Security | ████████████ Intermediate |

</div>

---

## 🧰 Tools & Technologies

<div align="center">

### 🔍 Recon & Enumeration
![Nmap](https://img.shields.io/badge/Nmap-0E83CD?style=for-the-badge&logoColor=white)
![Shodan](https://img.shields.io/badge/Shodan-FF0000?style=for-the-badge&logoColor=white)
![Subfinder](https://img.shields.io/badge/Subfinder-00ff41?style=for-the-badge&logoColor=black)
![Amass](https://img.shields.io/badge/Amass-333333?style=for-the-badge&logoColor=white)

### 💥 Exploitation & Testing
![Burp Suite](https://img.shields.io/badge/Burp_Suite-FF6633?style=for-the-badge&logoColor=white)
![Metasploit](https://img.shields.io/badge/Metasploit-2596CD?style=for-the-badge&logoColor=white)
![SQLMap](https://img.shields.io/badge/SQLMap-CC0000?style=for-the-badge&logoColor=white)
![Nikto](https://img.shields.io/badge/Nikto-222222?style=for-the-badge&logoColor=white)

### 🖥️ Platforms & OS
![Kali Linux](https://img.shields.io/badge/Kali_Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white)
![Windows](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)

### 🛡️ Network & Firewall
![Wireshark](https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white)
![pfSense](https://img.shields.io/badge/pfSense-212121?style=for-the-badge&logoColor=white)
![Nessus](https://img.shields.io/badge/Nessus-00AEEF?style=for-the-badge&logoColor=white)

</div>

---

## 📊 GitHub Stats

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=Suryaping01&show_icons=true&theme=chartreuse-dark&hide_border=true&bg_color=0d1117&title_color=00ff41&icon_color=00ff41&text_color=ffffff" width="48%" />

<img src="https://github-readme-streak-stats.herokuapp.com/?user=Suryaping01&theme=chartreuse-dark&hide_border=true&background=0d1117&ring=00ff41&fire=00ff41&currStreakLabel=00ff41" width="48%" />

</div>

---

## 🏆 Bug Bounty Platforms

<div align="center">

[![HackerOne](https://img.shields.io/badge/HackerOne-494649?style=for-the-badge&logo=hackerone&logoColor=white)](https://hackerone.com/)
[![Bugcrowd](https://img.shields.io/badge/Bugcrowd-F26822?style=for-the-badge&logo=bugcrowd&logoColor=white)](https://bugcrowd.com/)
[![Intigriti](https://img.shields.io/badge/Intigriti-1A1A2E?style=for-the-badge&logoColor=white)](https://intigriti.com/)

</div>

---

## 📜 Certifications & Learning Path

```
[✔] eJPT  - eLearnSecurity Junior Penetration Tester (Target)
[✔] CEH   - Certified Ethical Hacker (Learning)
[✔] CompTIA Security+ (DONE)
[ ] OSCP  - Ultimate Goal 🎯
```

---

## 🌐 Connect With Me

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)]([https://linkedin.com/in/suriyaprakashsekar](https://www.linkedin.com/in/suriyaprakash-sekar-79014123/))
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Suryaping01)
[![TryHackMe](https://img.shields.io/badge/TryHackMe-212C42?style=for-the-badge&logo=tryhackme&logoColor=white)]([https://tryhackme.com](https://tryhackme.com/p/surya.ping)/)

</div>

---

<div align="center">

```bash
┌──(suriya㉿kali)-[~]
└─$ echo "Thanks for visiting! Happy Hunting 🎯"

> "The quieter you become, the more you can hear." — Kali Linux
```

</div>
