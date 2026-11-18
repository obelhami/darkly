# Darkly v2 — Web Security Audit

**42 School — Holy Graph Curriculum**

A comprehensive security audit of Darkly v2, a deliberately vulnerable web application built with FastAPI and PocketBase. This project documents the discovery, exploitation, and remediation of security vulnerabilities, covering Broken Access Control, Authentication Failures, Injection Attacks, and other common web security weaknesses.

## Quick Start

Read [walkthrough.md](walkthrough.md) for the complete audit narrative, exploitation methodology, attack chains, captured flags, and security findings.

## Structure

```text
exploits/
│
├── 01_idor/                         # FLAG{1d0r_ur_pr0f1l3_1s_m1n3}
├── 02_insecure_password_reset/      # FLAG{r3s3t_t0k3n_w4s_just_md5_lol}
├── 03_unrestricted_upload/          # FLAG{unr3str1ct3d_upl0ad_g0_brrr}
├── 04_mass_assignment/              # FLAG{just_p4tch_y0ur_own_r0l3_lol}
├── 05_xxe_ssrf/                     # FLAG{d3fus3dxml_n3xt_spr1nt_pr0m1s3}
├── 06_pocketbase_admin/             # FLAG{th3_und3rsc0r3_sl4sh_kn0ws_th3_w4y}
│
├── BONUS_01_unprotected_api/        # FLAG{md5_1s_4_n4m3pl4t3_n0t_4_l0ck}
├── BONUS_02_stored_xss/             # FLAG{xss_st0r3d_1s_n0t_4_f34tur3_n0w}
├── BONUS_03_path_traversal/         # FLAG{d0t_d0t_sl4sh_4ll_th3_w4y_d0wn}
├── BONUS_04_csrf/                   # FLAG{csrf_4ny_0r1g1n_1s_w3lc0m3}
│
├── VULN_01_non_httponly_cookie/
├── VULN_02_reflected_xss_newsletter/
├── VULN_03_unauthenticated_docs_internal/
├── VULN_04_header_info_disclosure/
├── VULN_05_console_debug_disclosure/
├── VULN_06_open_redirect/
├── VULN_07_no_rate_limit_weak_password/
├── VULN_08_missing_security_headers/
├── VULN_09_jwt_forgery/
└── VULN_10_base64_obscurity/
```

Each vulnerability folder contains:

- `explanation.md` — vulnerability description, technical analysis, impact, and remediation.
- `exploit.sh` — automated script to reproduce the vulnerability.
- `flag` — captured flag, when applicable.

## Audit Statistics

| Metric | Count |
|---|---:|
| Total flags found | 10/10 |
| Mandatory flags | 6/6 |
| Bonus flags | 4/4 |
| Total vulnerabilities documented | 20 |
| Flag-bearing vulnerabilities | 10 |
| Additional vulnerabilities (no flag) | 10 |

## Vulnerability Coverage

The audit covers several important web security categories:

- **Broken Access Control** — IDOR, privilege escalation, and unauthorized API access.
- **Authentication Failures** — insecure password reset, weak password policies, and JWT-related weaknesses.
- **Injection Attacks** — XXE, SSRF, and Cross-Site Scripting (XSS).
- **Security Misconfiguration** — exposed administrative interfaces, missing security headers, and information disclosure.
- **File Handling** — unrestricted file upload and path traversal.
- **Request Integrity** — Cross-Site Request Forgery (CSRF).
- **Session Management** — insecure cookie configuration.

## Target Environment

| Component | Details |
|---|---|
| Application | Darkly v2 |
| Backend | FastAPI 0.104 |
| Database / Backend service | PocketBase 0.22.4 |
| Language | Python 3.11 |
| Application URL | `http://localhost:4942` |
| PocketBase URL | `http://localhost:8090` |

## Methodology

The audit follows a practical penetration-testing workflow:

1. **Reconnaissance** — identify application endpoints, exposed services, and attack surfaces.
2. **Enumeration** — inspect authentication mechanisms, API routes, user roles, and application behavior.
3. **Vulnerability Discovery** — identify weaknesses in authorization, input validation, session management, and configuration.
4. **Exploitation** — reproduce vulnerabilities and demonstrate their security impact.
5. **Flag Collection** — capture proof of successful exploitation.
6. **Documentation** — explain each finding, its impact, and recommended remediation.

## Security References

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Common Weakness Enumeration (CWE)](https://cwe.mitre.org/)
- [OWASP Web Security Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
- [PortSwigger Web Security Academy](https://portswigger.net/web-security)

## Author

**Omar Belhamid**

42 Network — 1337 Benguerir  
Holy Graph Curriculum