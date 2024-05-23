TITLE: Detecting and Auto-repairing Vulnerabilities in Role-based Access Control in Web Application

# DRacv:
Traditional methods for analyzing Broken Access Control (BAC) vulnerabilities have limitations regarding low coverage of access control rules, high false positive rate (FPR), and low detection efficiency. Additionally, state-of-the-art strategies for repairing BAC vulnerabilities utilizing statement-level replacement as a repair method may introduce new logical errors. To address these challenges, we propose a novel approach called DRacv (Detect and Repair Access Control Vulnerabilities) to identify and auto-repair vulnerabilities in Role-Based Access Control(RBAC) mode used in web applications. To detect vulnerabilities, DRacv first constructs a Fine-grained Global Multi-attribute Architectural Navigation Graph model (FG-MANG) for web applications through dynamic execution and static analysis, which characterizes full relationships between roles, privileges, and accessible page resources. Based on access control rules extracted from FG-MANG, DRacv generates targeted attack payloads to detect BAC vulnerabilities, significantly reducing FPR and eliminating redundant attack payloads. To auto-repair the identified vulnerabilities, DRacv first precisely extracts access control privilege parameters, validation functions, and contextual statements to construct the patch code templates. These templates generate user- and role-level verification patch codes for different users and roles. Instead of changing the vulnerable code, the patch codes behave like firewalls. They are added as separate files and invoked by the web page with vulnerability to defend against access control compromises. DRacv was evaluated on 12 popular open-source web applications in PHP and JAVA. From the applications, DRacv identified 35 vulnerabilities (11 were new) with only one false positive, achieving an FPR of 2.78%. We also compared DRacv's detection results with state-of-the-art studies. Results show that DRacv outperforms those studies regarding the number of vulnerabilities detected and FPR. Among the 35 vulnerabilities detected, DRacv automatically repaired 34 of them, achieving a repairate of 97.14%. The evaluation results also show that DRacv auto-fixed 18% and 70% more vulnerabilities than the two state-of-the-art auto repairing methods, respectively.

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
