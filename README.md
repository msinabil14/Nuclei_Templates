# 🎯 Nuclei Templates

A large personal collection of **50,000+ [Nuclei](https://github.com/projectdiscovery/nuclei) templates** organized by vulnerability type, for vulnerability scanning, misconfiguration detection, exposure discovery, and security research.

![Nuclei](https://img.shields.io/badge/Nuclei-Templates-blue)
![Templates](https://img.shields.io/badge/Templates-50K%2B-orange)
![Maintained](https://img.shields.io/badge/Maintained-Yes-brightgreen)

---

## 📖 About

This repository gathers Nuclei YAML templates into category-based folders so you can quickly pick the right templates for a bug bounty target, a pentest, or research. Instead of running everything, you can point Nuclei at a single category (e.g. `XSS/` or `SQL_Injection/`).

## 📂 Repository Structure

| Folder | Templates | Description |
|--------|-----------|-------------|
| `possible_cves/` | ~12,000 | CVE templates, organised by year (2000–2023) |
| `WordPress_Plugin_Theme_Other/` | ~7,700 | WordPress plugin / theme vulnerabilities |
| `XSS/` | ~6,700 | Cross-Site Scripting |
| `others 2.0/` | ~5,300 | Templates by protocol: `http`, `dns`, `file`, `network`, `ssl`, `cloud`, `code`, `headless`, `javascript`, `dast`, `workflows` |
| `Other/` | ~3,900 | Miscellaneous templates |
| `tech_detection/` | ~2,300 | Technology / fingerprint detection |
| `Info_Disclosure_Exposed_Files/` | ~1,900 | Information disclosure & exposed files |
| `SQL_Injection/` | ~1,600 | SQL Injection |
| `misconfiguration/` | ~1,400 | Security misconfigurations |
| `RCE_Command_Injection/` | ~1,200 | Remote Code Execution & Command Injection |
| `LFI_Path_Traversal_File_Read/` | ~1,200 | LFI, Path Traversal, Arbitrary File Read |
| `exposed-panels/` | ~1,100 | Exposed admin / login panels (by vendor) |
| `Auth_Bypass_Unauth_Access/` | ~1,050 | Authentication bypass & unauthorized access |
| `File_Upload/` | ~800 | Arbitrary file upload |
| `OSINT_Username_Check/` | ~630 | Username / social-media presence checks |
| `Malware_Backdoor_Webshell/` | ~380 | Malware, backdoors, webshells |
| `Open_Redirect/` | ~370 | Open Redirect |
| `misconfigured_login/` | ~320 | Misconfigured / default login pages |
| `SSRF/` | ~320 | Server-Side Request Forgery |
| `exposed_tokens/` | ~220 | Leaked API keys & tokens (by service) |
| `Privilege_Escalation/` | ~110 | Privilege escalation |
| `Subdomain_Takeover/` | ~100 | Subdomain takeover |
| `wordpress/` | ~100 | WordPress-specific checks |
| `DoS/` | ~60 | Denial of Service |
| `Deserialization_Log4j/` | ~55 | Deserialization & Log4j |
| `XXE/` | ~40 | XML External Entity |
| `CRLF_HostHeader_Smuggling/` | ~35 | CRLF, Host Header injection, Request Smuggling |
| `SSTI/` | ~15 | Server-Side Template Injection |
| `CSRF/` | ~8 | Cross-Site Request Forgery |

## ⚙️ Installation

Install Nuclei (requires Go):

```bash
go install -v github.com/projectdiscovery/nuclei/v3/cmd/nuclei@latest
```

Or download a binary from the [official releases](https://github.com/projectdiscovery/nuclei/releases).

Clone this repository:

```bash
git clone https://github.com/msinabil14/Nuclei_Templates.git
cd Nuclei_Templates
```

> ⚠️ The repo is large (50K+ files). For a faster clone use `git clone --depth 1`.

## 🚀 Usage

Scan a target with a specific category:

```bash
nuclei -u https://example.com -t XSS/
nuclei -u https://example.com -t SQL_Injection/
nuclei -u https://example.com -t exposed-panels/
```

Scan a CVE year folder:

```bash
nuclei -u https://example.com -t possible_cves/2023/
```

Folders with spaces must be quoted:

```bash
nuclei -u https://example.com -t "others 2.0/http/"
```

Scan a list of targets:

```bash
nuclei -l targets.txt -t LFI_Path_Traversal_File_Read/ -o results.txt
```

Filter by severity:

```bash
nuclei -l targets.txt -t possible_cves/ -severity critical,high
```

Run a single template:

```bash
nuclei -u https://example.com -t SSRF/template-name.yaml
```

Validate templates:

```bash
nuclei -t SSTI/ -validate
```

## 💡 Tips

- Running all 50K+ templates at once is slow and noisy. Start with a category that matches your target.
- Use `-rate-limit` and `-c` to control speed and avoid overloading targets.
- Use `-tags` and `-severity` to narrow down results.
- Some templates may be outdated or produce false positives; always verify findings manually.

## 🤝 Contributing

Suggestions and improvements are welcome:

1. Fork this repository
2. Create a branch (`git checkout -b add-new-templates`)
3. Add your template to the matching category folder
4. Validate it with `nuclei -t your-template.yaml -validate`
5. Commit and open a Pull Request

## ⚠️ Disclaimer

These templates are provided **for educational purposes and authorized security testing only**. Only scan systems you own or have explicit written permission to test. The author is not responsible for any misuse or damage.

## 🙏 Credits

Many templates are collected from the community and from [ProjectDiscovery's nuclei-templates](https://github.com/projectdiscovery/nuclei-templates) & https://github.com/linuxadi/40k-nuclei-templates. All credit goes to the original authors.

## 👤 Author

**msinabil14** – [@msinabil14](https://github.com/msinabil14)

⭐ If this repository helps you, please give it a star!
