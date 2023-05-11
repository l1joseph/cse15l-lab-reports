Hey, 
Back for even more?

---

Today we'll be taking a deep dive into the grep command.

What is the grep command. The grep in the grep command stands for 'global regular expression print'. It is a that is command used to search and match text contained in standard output and text files.

Grep has tons on interesting command line options we can explore.

## 1. **Grep -o**

```bash
leojo@BobtheBuilder MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep -o "Six large controlled" */1468-6708-3-1.txt     
Six large controlled
```

```bash
leojo@BobtheBuilder MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep -o "President Clinton" */chapter-6.txt
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
President Clinton
```

In each of the above examples grep -o prints matched parts of a matching line only, instead of the whole line. It also separates each such match onto a serparate output line. For example, the first example shows trying to fine a specific case-matched phrase. While the second example shows all instances of 'President Clinton' within a file. The utility of this is pretty self evident, being able to use it as a ctrl+f type command to return only the string you want.

---

## 2. **Grep -i**

```bash
leojo@BobtheBuilder MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep -i "GENeral agreeMEnt" */*/DraftRecom-PDF.txt     
significant and general agreement. He indicated the process would
```
```bash
leojo@BobtheBuilder MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep -i "khalid sheikh" */chapter-13.4.txt
            2. Those detainees are Khalid Sheikh Mohammed, Abu Zubaydah, Riduan Isamuddin (also
```

In each of these examples, we see that the capilization of the search term does not match the capitalization of the returned results. Grep -i makes it so that the input string and search is not case sensitive and instead returns any lines where the characters match, even if the capalizations do not. This is usefule to find names or to find strings where you are not sure of the capalization of certain terns, such as 'Khalid Sheikh' or miscapilization things like the first grep -i example.

---

## 3. **Grep -w**

```bash
leojo@BobtheBuilder MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep -w "so" */1468-6708-3-4.txt
        the study (the so-called 'withdrawals') include death,
        simple algebra can show that this is always so. We can see
        though, because every so-called informative missing data
        test, and so on. Example 3 also used a ranking method after
        reaction', 'patient refusal', and so on. Within the same
```
``` bash
leojo@BobtheBuilder MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep  "so" */1468-6708-3-4.txt
        measurements. Possible reasons for patients dropping out of
        the study (the so-called 'withdrawals') include death,
        the awareness of the problem and to provide some general
          whatever the reason, or performed although compliance
          24 weeks. Listed reasons (and number of patients) for
          other reasons' (n = 10).
          ventricular mass, and coronary vasodilatory in patients
          omapatrilat with hydrochlorothiazide in comparison with
        unrealistic since some people withdrew because of lack of
        response and some because of side effects, but the paper
        (d)dropouts would have also responded, had they completed
        simple algebra can show that this is always so. We can see
        comparison of the estimates. Unfortunately, the paper did
        Lessons learned
        • It is important to record and report the reasons for
        withdrawal according to their treatment group. The reasons
        found in the reason for the dropout and this can be used to
        Association class IV) and they are unable to perform
        also be equal to zero seconds, and not simply regarded as
        missing data. For the same reason, the remaining survival
        not a censored observation when doing, say Kaplan-Meier,
        censoring because of loss-to-follow-up or
        consideration into account, although they may also be
        patients being administratively 'censored'. We have seen
          situation. It is also known as a 'question for
          question, also known as the 'question for pragmatic
          design. However, other endpoints may also be followed-up
          software [ 12 13 ] . However, the complexity of
          the treatment groups, the relative comparison of the
        Other, more sophisticated methods based on statistical
        though, because every so-called informative missing data
        test, and so on. Example 3 also used a ranking method after
        missing data, according to the reasons for withdrawals [ 21
        reaction', 'patient refusal', and so on. Within the same
        data information and strong faith in the reasons given for
        Composite comparisons
        Association's draft guidance on diabetes trials
        pattern of compliance. The comparison (a) is
        techniques. The comparison (b) requires the same care as
        comparison [ 28 ] . Generally speaking, in an observational
        during trial monitoring. A truly ITT design is absolutely
        instead of a blank. Consideration may also be given to
 ```
 
 ```bash
 
leojo@BobtheBuilder MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep -w  "chose" */preface.txt
```
```bash
leojo@BobtheBuilder MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep  "chose" */preface.txt
                Democrats chosen by elected leaders from our nation's capital at a time of great
```

In the above examples, there are two different searches for the same term (so & chose). One uses grep-w, and the other does not. The grep -w command seems to return much fewer results. When we look into why, we can see that it checks for whole words and not just occurances of the string, thus it eliminates all options where the search term is part of a substring of another word/string. This can be extremely useful to find words, and to remove cluttered results that aren't the word you are looking for.

---

## 4. **Grep -R**

```bash
leojo@BobtheBuilder MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep -wR selected 911report/
911report/chapter-1.txt:    When he checked in for his flight to Boston, Atta was selected by a computerized prescreening system known as CAPPS (Computer Assisted Passenger Prescreening System), created to identify passengers who should be subject to special security measures. Under security rules in place at the time, the only consequence of Atta's selection by CAPPS was that his checked bags were held off the plane until it was confirmed that he had boarded the aircraft. This did not hinder Atta's plans.
911report/chapter-1.txt:    While Atta had been selected by CAPPS in Portland, three members of his hijacking team-Suqami, Wail al Shehri, and Waleed al Shehri-were selected in Boston. Their selection affected only the handling of their checked bags, not their screening at the checkpoint. All five men cleared the checkpoint and made their way to the gate for American 11. Atta, Omari, and Suqami took their seats in business class (seats 8D, 8G, and 10B, respectively). The Shehri brothers had adjacent seats in row 2 (Wail in 2A, Waleed in 2B), in the firstclass cabin. They boarded American 11 between 7:31 and 7:40. The aircraft pushed back from the gate at 7:40.
911report/chapter-1.txt:    Shehhi and his team, none of whom had been selected by CAPPS, boarded United 175 between 7:23 and 7:28 (Banihammad in 2A, Shehri in 2B, Shehhi in 6C, Hamza al Ghamdi in 9C, and Ahmed al Ghamdi in 9D). Their aircraft pushed back from the gate just before 8:00.
911report/chapter-1.txt:    Hani Hanjour, Khalid al Mihdhar, and Majed Moqed were flagged by CAPPS. The Hazmi brothers were also selected for extra scrutiny by the airline's customer service representative at the check-in counter. He did so because one of the brothers did not have photo identification nor could he understand English, and because the agent found both of the passengers to be suspicious. The only consequence of their selection was that their checked bags were held off the plane until it was confirmed that they had boarded the aircraft.
911report/chapter-1.txt:    Newark: United 93. Between 7:03 and 7:39, Saeed al Ghamdi, Ahmed al Nami, Ahmad al Haznawi, and Ziad Jarrah checked in at the United Airlines ticket counter for Flight 93, going to Los Angeles. Two checked bags; two did not. Haznawi was selected by CAPPS. His checked bag was screened for explosives and then loaded on the plane.
911report/chapter-12.txt:                    on passengers. As a start, each individual selected for special screening should
911report/chapter-13.1.txt:                Before the election, candidates should submit the names of selected members of
911report/chapter-13.2.txt:                Logan was selected for two of the hijackings (as were both American and United
911report/chapter-13.2.txt:                16, 2004). It appears that Atta was selected at random. See Al Hickson briefing
911report/chapter-13.3.txt:                algorithm, a number of other passengers were selected at random, both to address
911report/chapter-13.4.txt:                selected to be hijackers who ultimately did not participate. For many of these
911report/chapter-13.4.txt:                operation as examples. In the planes operation, Khallad notes, Bin Ladin selected
911report/chapter-13.5.txt:                endorsement of Bin Ladin. He was not ultimately selected for the 9/11 attacks
911report/chapter-13.5.txt:                According to Binalshibh, Atta deliberately selected morning flights because he
911report/chapter-13.5.txt:                Commission selected four representatives-the Chair, the Vice Chair, Commissioner
911report/chapter-3.txt:                be selected by CAPPS for additional scrutiny. Selection entailed only having one's
911report/chapter-3.txt:                Intelligence Brief-or, better still, selected for inclusion in the President's Daily
911report/chapter-3.txt:                compiled the results, and passed selected reports to appropriate stations, the
911report/chapter-5.txt:            Bin Ladin also soon selected four individuals to serve as suicide operatives: Khalid
911report/chapter-5.txt:                selected by Bin Ladin for the planes operation were chosen to attend an elite
911report/chapter-5.txt:                selected the veteran fighters who received this training, and several of them were
911report/chapter-5.txt:                insisted that everyone he had selected receive the training.
911report/chapter-5.txt:                selected so quickly-before comprehensive testing in the training camps or in
911report/chapter-5.txt:                had been selected to join the plot, and they received additional funds for travel
911report/chapter-6.txt:                Bin Ladin. He chose the target and location of the attack, selected the suicide
911report/chapter-6.txt:                For secretary of defense he selected Donald Rumsfeld, a former member of Congress,
911report/chapter-7.txt:                suicide operatives, and eventually were selected as muscle hijackers for the planes
911report/chapter-7.txt:                to be known to international security agencies were purposefully selected for the
911report/chapter-7.txt:                minutes, and that many of the 9/11 hijackers were selected in this manner. Bin
911report/chapter-7.txt:                muscle hijackers, Bin Ladin apparently selected at least nine other Saudis who, for
911report/chapter-7.txt:            Our knowledge of the international travels of the al Qaeda operatives selected for
911report/chapter-7.txt:                operation only because Moussaoui had been selected and assigned by Bin Ladin
911report/chapter-7.txt:            It therefore appears that the attack date was selected by the third week of August.
911report/chapter-9.txt:                advance notice to tenants." Fire safety teams"were selected from among civilian
```
```bash
leojo@BobtheBuilder MINGW64 ~/Documents/GitHub/docsearch/technical (main)
$ grep -iR connecticut 911report/
911report/chapter-1.txt:    At 8:52, in Easton, Connecticut, a man named Lee Hanson received a phone call from his son Peter, a passenger on United 175. His son told him: "I think they've taken over the cockpit-An attendant has been stabbed- and someone else up front may have been killed. The plane is making strange moves. Call United Airlines-Tell them it's Flight 175, Boston to LA." Lee Hanson then called the Easton Police Department and relayed what he had heard.
911report/chapter-13.3.txt:            113. Rep. Christopher Shays of Connecticut, chairman of the National Security
911report/chapter-13.4.txt:                Connecticut and New Jersey, see FBI report, "Hijackers Timeline," Dec. 5, 2003 (May
911report/chapter-13.4.txt:                265A-NY-280350-NH, serial 1859). For return to Connecticut and Rababah not seeing
911report/chapter-7.txt:            Rababah, who had lived in Connecticut, New York, and New Jersey, told investigators
911report/chapter-7.txt:                then suggested that Hazmi and Hanjour travel with him to Connecticut where they
911report/chapter-7.txt:                to Connecticut. There he says he found them with new roommates-Ahmed al Ghamdi and
911report/chapter-7.txt:                Connecticut, followed by Hazmi, who had Moqed and Ghamdi in his car. After a short
911report/chapter-7.txt:                stay in Connecticut, where they apparently called area flight schools and real
911report/chapter-7.txt:                Hanjour were about to leave for Connecticut and New Jersey. As the summer
```

Here we can see that the grep -R command allows us to search recurvely through directories for instances of our search string. We can also see that we can pair command line options together. Grep -wR searches for instances of a word recursively throughout a directory, while grep -iR searches for a string irrespective of capitalization. This is useful because now we can grep through the contents of whole directories instead of going into each individual file/folder in a directory.

---
**Sources**

The source I used to identify and understand these commands was the [GeeksforGeeks](https://www.geeksforgeeks.org/grep-command-in-unixlinux/) website on grep commands.
