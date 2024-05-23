# DRacv:
Traditional methods for analyzing Broken Access Control (BAC) vulnerabilities have limitations regarding low
coverage of access control rules, high false positive rate (FPR), and low detection efficiency. Additionally, state-
of-the-art strategies for repairing BAC vulnerabilities utilizing statement-level replacement as a repair method
may introduce new logical errors. To address these challenges, we propose a novel approach called DRacv
(Detect and Repair Access Control Vulnerabilities) to identify and auto-repair vulnerabilities in Role-Based
Access Control (RBAC) mode used in web applications. Firstly, DRacv constructs a Fine-grained Global Multi-
attribute Architectural Navigation Graph model (FG-MANG) for web applications through dynamic execution
and static analysis, which characterizes full relationships between roles, privileges, and accessible page
resources. Based on access control rules extracted from FG-MANG, DRacv generates targeted attack payloads
to detect BAC vulnerabilities, significantly reducing FPR and eliminating redundant attack payloads. DRacv
precisely extracts access control privilege parameters, validation functions, and their contextual statements to
construct the patch code templates. These templates then generate user- and role-level verification patch codes
for different users and roles. Instead of changing the vulnerable code, the patch codes behave like firewalls.
They are added as separate files and invoked by the web page with vulnerability pages to defend against access
control compromises. DRacv was evaluated on 12 popular open-source web applications in PHP and JAVA
and compared with state-of-the-art methods.

## Requirements

- Recommend to use Anaconda3 
- python==3.7
- bs4==0.02
- selenium==4.11.2



# Instruction:
### crawling
    $ run demo_general.py
### attack
    $ run generateAttack1.py
### locate access control code gadget 
    $ run visitEveryPage_demo.py
    $ run visitEveryPage1
### repair
    $ run repairVulnerability.py 


# Test Suite 
1. Phpns -- https://sourceforge.net/projects/phpns/
2. AWCM -- https://sourceforge.net/projects/awcm/
3. PHPOLL -- https://sourceforge.net/projects/phpoll/
4. Bwapp -- https://sourceforge.net/projects/bwapp/
5. DVWA -- www.dvwa.co.uk
6. SCARF -- www.sourceforge.net/projects/scarf/files/
7. Events Lister -- www.exploit-db.com/exploits/17554/
8. MyBloggie -- https://www.exploit-db.com/apps/44920560d3015356c253efb31ce1fe6e-mybloggie216.zip
9. Mybb -- https://github.com/mybb
10. Wackopicko -- https://github.com/DTTAST/WackoPicko
11. JsForum -- https://sourceforge.net/projects/jsforum/
12. OnlineStore -- https://github.com/manhduydl/Shopping-web-Jsp-Servlet
