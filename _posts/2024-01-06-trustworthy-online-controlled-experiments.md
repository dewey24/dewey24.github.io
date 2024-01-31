---
title: <br/><br/><br/>Trustworthy Online Controlled Experiments<br/><br/><br/>
date: "10 Jan 2024"
layout: single
# classes: wide
author_profile: true
header:
  overlay_image: /assets/images/walle.jpeg
  #overlay_color: "#333"
  show_overlay_excerpt: false
  teaser: /assets/images/experiments.jpeg
tags:
- "Machine Learning"
- "Deep Learning"
- Analytics
- AI
toc: true
---

# Notes from this "Must Read" book

<img src="/assets/images/experiments.jpeg" alt="experiments" class="inline" width="250" height="350"/>


## <ins>**1. Use Scientific Method:**</ins> 
1. Observation
2. Question
3. Hypothesis
4. Experiment
5. Analysis of Results
6. Conclusion


### <ins>**Twyman's Law**</ins> - Any statistic that looks interesting or different is usually wrong
* Double check results (too good to be true?)
* Run validity tests (especially for breakthrough positive results)

_________________________________________________________________________________________________________________________________________________________________________________


## <ins>**2. Online Randomized Controlled Experiments | A/B Testing**</ins>
* Changes to UI
* Relevance Algorithms (search, ads, personalization, recommendations)
* Latency / Performance
* Content Management Systems
* Customer Support Systems

(User interactions are instrumented i.e. monitored & logged. From the logged data, metrics are computed, which allow us to assess the difference between the variants for each metric)

### <ins>**Multiple Channels**</ins>
* Websites
* Desktop Applications
* Mobile
* Email

_________________________________________________________________________________________________________________________________________________________________________________

## <ins>**3. Controlled Experiments Terminology:**</ins> 
* **Overall Evaluation Criterion (OEC)** - OEC can be a combination of usage (sessions per user), relevance (successful sessions / time to success) and ads revenue. OEC should be measurable in a short period, sensitive enough to show differences and predictive of long-term goals.

* **Parameters** - Also, called factors / levels / variables. e.g. - font color, font size

* **Variant** - Control & Treatment

* **Randomization Unit** - A pseudo-randomization process is applied to units (e.g. - users / pages / sessions). We must map units to variants in a persistent manner (i.e. if user is the randomization unit, a user should consistently see the same experience)

* **Affected Users** - To not dilute results only analyze metrics for the potentially affected users and exclude unaffected users. e.g. - Users who start the purchase (in the checkout funnel) VERSUS users who viewed the site or users who completed the purchase

_________________________________________________________________________________________________________________________________________________________________________________

## <ins>**4. Common Pitfalls**</ins>
* If every user should see either Control or Treatment from a certain time; then having many users in both variants is a red flag
* If experiment design calls for equal percentages in the two variants; then large deviations that are probablistic unlikely should likewise raise questions

### <ins>_4.1 Misinterpretation of Statistical Results_</ins>
* **Lack of Statistical Power**
  * If an experiment impacts only a small subset of the population, it is important to analyze just the impacted subset
* **Misinterpreting p-values**
  * Believing that p-value represents probability that the avg. metric value in Control is different than Treatment
* **Peeking at p-values**
  * Continuously monitoring p-values while running an online controlled experiment
* **Multiple Hypothesis Tests**
  * Looking at multiple metrics
  * Looking at p-values across time (peeking)
  * Looking at segments of the population
  * Looking at multiple iterations of an experiment
* **Confidence Interval**
  * A common mistake is to look at the CI separately for Control & Treatment. And assume if they overlap the Treatment effect is not statistically significant
  * Another common misunderstanding about CI is believing 95% CI has a 95% chance of containing p-value

________________

### <ins>_4.2 Threats to Internal Validity_</ins>

Experiment study should establish trustworth cause-and-effect relationship and avoid confounding variables

* **Selection Bias**
* **Non-Compliance**
* **Interference**
* **Time Effects**
* **Placebo Effects**

* **Violations of SUTVA (Stable Unit Treatment Value Assumption)**
  * Experiment units shouldn't affect each other
  * Social Networks - where a feature might spillover to a user's network
  * Document authoring tools - co-authoring support
  * Two-sided marketplaces
  * Shared resources (such as CPU, storage & caches)
* **Survivorship Bias**
  * Analyzing users who have benn active for some time introduces survivorship bias
  * Example : WW II - Bombers / Armor / Bullet Hole (add armor where no holes as those bombers never made it back)
* **Intention-to-Treat or Non-Compliance**
  * Use the initial assignment whether it was executed or not
* **Sample Ratio Mismatch**
  * If the experiment design was for equal allocations to both variants, then by design you should get a ratio close to 1.0 (can do hypothesis testing for sampling ratio)
  * _**Browser redirects**_ - Avoid this while implementing A/B testing and redirect Treatment to a different page. Instead use server-side mechanism.
    * Performance difference - Treatment experiences extra redirect
    * Bots - Bots handle redirects differently
    * Interference - Treatment users may bookmark the page and share it with Control users
  * _**Lossy Instrumentation**_ - Click tracking with web-beacons is known to be lossy (not all clicks get recorded) and Treatment can sometimes impact loss rate and thus, impact SRM
  * _**Residual or carryover effects**_ - New code (for an experimental feature) may inroduce bugs and impact some Treatment users even if experiment was aborted. Therefore, run pre-experiment A/A tests to check any residual effects / SRM and re-randomize if have to. Browser cookies can create carryover effect (not reset the message exposure count) if an experiment is restarted.
  * _**Bad Hash function for Randomization**_ - Cryptographic hash functions like MD5 are good but slow. A non-cryptographic function used by Microsoft is Jenkins / Spookyhash
  * _**Triggering impacted by treatment**_ - If triggering users into experiment is done based on attributes changing over time, then you must ensure that no attributes used for triggering could be impacted by the Treatment
  * _**Time-of-Day Effects**_ - Sending email to Control during work hours whereas sending email to Treatment during after work.
  * _**Data Pipeline**_ - Bot filtering is a serious problem especially for search engines. Some of the most heavily engaged users as an effect of Treatment maybe incorrectly classified as bots and removed from analysis. Thus, an SRM check is critical

________________

### <ins>_4.3 Threats to External Validity_</ins>

Not generalizing to other populations or time periods

* **Sampling Error / Bias**
* **Primacy Effect**
  * When a change is introduced, users may need time to adapt as they are primed in the old feature.
* **Novelty Effect**
  * Initial newness attraction effect which is un-sustained
* **Approach**
  * Run the experiment for a longer time and let the effect stabilize
  * Plot the effect over time and see if its increasing / decreasing. Treatment effect should be constant over time.
  * Plot the effect over time only for the users that appeared in the first day or two

_________________________________________________________________________________________________________________________________________________________________________________

## <ins>**5. Segment Differences:**</ins> 

### 5.1 What are good segments?
* _**Market or country / Language**_
* _**Service or platform**_
  * Platform - iOS vs Android vs Windows
    * Click tracking - iOS & Windows use redirects to track the clicks. Android tracks clicks with web beacon.
  * Interface - Website / Desktop Application / Mobile Application
  * Mobile manufacturer (Samsung vs Motorola) - provide add-ons that can cause features to fail
* _**Time of day and day of week**_
* _**User type: new or existing**_
* _**User account characterstics: single or shared; single or family**_

### 5.2 Segmented views are commonly used two ways:
1. Segmented view of a metric, independent of any experiment
2. Segmented view of the Treatment effect for a metric
   * Heterogeneous treatment effects - indicating that the Treatment effect is not homogeneous or uniform across different segments

### 5.3 Simpson's paradox:
* It is mathematically possible for a drug to increase the probability of recovery in the aggregate population yet decrease the probability in every sub-population
### 5.4 "Sure thing principal" Theorem
* If an action increases the probability of an event in each sub-population, it must also increase the probability of an event in population as a whole


_________________________________________________________________________________________________________________________________________________________________________________

## <ins>**6. Speed Matters:**</ins> 

### 6.1 Slowdown experiments: How important is the latency?
1. At Amazon, a 100 msec slowdown experiment decreased sales by 1%
2. At Bing, a 100 msec speedup improves revenue by 0.6% (other key metrics: distinct queries, clicks, satisfaction, time-to-click, churn, CTR, revenue per user)

### 6.2 Key assumption: local linear approximation

### 6.3 Perceived Performance for PLT (page load time)
* Time to first result
* Above the Fold Time (AFT)
* Speed Index
* Page Phase Time & User Ready Time

_________________________________________________________________________________________________________________________________________________________________________________

## <ins>**7. Organizational Metrics:**</ins> 

## 7.1 Metrics Taxonomy
### OKR (Objectives & Key Results)
### Goal / Sucess / North Star metrics
  * Usually a single or very small set of metrics
### Driver / Sign-post / Surrogate / Indirect / Predictive metrics
  * Tend to be shorter-term, faster moving and more sensitive
  * HEART framework (Happiness, Engagement, Adoption, Retention and Task Success)
  * AARRR framework (Acquistion, Activation, Retention, Referral and Revenue)
  * A good driver metric indicates that we are moving in the right direction to move the goal metrics)
### Guardrail metrics
  * More sensistive than Goal or Driver metrics
  * Two types:
    * metrics that protect the business
    * metrics that assess he trustworthiness and internal validity of experiments
  * Type 1:
    * password management: security VERSUS ease-of use & accessibility
    * new UI: page load time
    * registrations VERSUS per-user engagement
    * latency
    * HTML response size per page
    * Javascript errors per page - segmented by browsers to see if its browser dependent
    * revenue-per-user (or more sensitive - was there revenue for user, yes/no)
    * pageviews-per-user
    * client crashes / crash rate
  * Type 2:
    * Data quality metrics - ensure the internal validity & trustworthiness
### Granular metrics
  * Page CTR can be broken into CTR on dozens of features on the page
### Diagnosis or debug metrics


## 7.2 Formulating Metrics: Principles & Techniques

### Ensure Goal metrics are:
* Simple
* Stable

### Ensure Driver metrics are:
* Aligned with the goal
* Actionable and relevant
* Sensitive
* Resistant to gaming

_________________________________________________________________________________________________________________________________________________________________________________

## <ins>**8. Overall evaluation criterion:**</ins> 

### OEC must be:
1. Measurable
  * Bad Example: post-purchase satisfaction can be challenging to measure
3. Attributable
  * Bad Example: metrics provided by 3rd partities may not be attributable to experiment variants
5. Sensitive and timely
  * Bad Example: stock-price is not a timely and sensitive metric for new feature experimentation / subscription renewal rate
  * Good Example: CTR accounting for (quick-backs), Purchase, Time-to-success, Usage
7. Computable


### OEC: weighted combination of several key goal and driver metrics (after normalization)

### Example 1: Amazon email campaign

$$ OEC = ( \sum_{i=1}^n Rev_i - (s  \*  ULL)) / n $$
$$ ULL = Unsubscribe Lifetime Loss $$
* i ranges over e-mail recipients for the variant
* s is the number of unsubscribes in the variant
* n is the number of users in the variant
* Unsubscribe Lifetime Loss is the estimated revenue loss for not being able to email a person for life

### Example 1: Bing's search engine

$$ Distinct queries = n (Users / Month)  \*  (Sessions / User)  \*  (Distinct queries / Session) $$





_________________________________________________________________________________________________________________________________________________________________________________

## <ins>**9. Quotes:**</ins> 
* One accurate measurement is worth more than a thousand expert opinions
* We are poor at assessing the value of ideas. 80% of the time you/we are wrong about what a customer wants
* Any statistic that looks interesting or different is usually wrong
  * Error in instrumentation / logging
  * Loss of data / duplication
  * Computational error
* Fast is my favorite feature
* If you can't measure it, you can't improve it

_________________________________________________________________________________________________________________________________________________________________________________

## <ins>**10. Interesting Anecdotes:**</ins> 

### **1. Microsoft Bing:**

* Bing search engine: Lengthen the title line of ads by combining it with the text from the first line below title
* Impact: 12% increase in Revenue i.e. $100M
* Without significantly hurting user-experience
* Overall Evaluation Criterion (OEC): Weighs "Revenue" against UX metrics like "Sessions per user"


### **2. Microsoft Office 365:**

* Office 365 users that see error messages and experience crashes have lower churn rates
* But that doesn't mean Office 365 should show more error messages or Microsoft should lower code quality
* All three events are caused by a single omitted factor: usage. Heavy users of the product see more error messages, experince more crashes and have lower churn rate


### **3. Microsoft & Google Color Schemes:**

* Microsoft - Bing color tweaks showed significant impact on users' success rate, time to success & monetization
* Google - Tested 41 gradations of blue. Tweaks to color scheme resulted in significant positive impact on user engagement


### **4. Amazon Credit Card Offer**

* Amazon's credit card offer on home page was highly profitable but had lower CTR
* Amazon experimentation team moved the offer to shopping cart page with simple math highlighting the savings user will receive. Since, users adding an item to the shopping cart have clear purchase intent, this offer displays at the right time. This change resulted in significant increase in profit without impacting CTR.

### **5. Amazon Shopping Cart Recommendation**

* Contrary to marketing Senior-VP hunch of feature being distraction, Shopping Cart feature had significant positive impact

### **6. Microsoft, Amazon & Google Search Engine Performance Improvements**

* Microsoft - Change the way javascript was generated and shortened the HTML sent to clients significantly and resulting in improved performance and key metrics. E.g. - success rate and time to success
* Amazon - A 100th milisecond slowdown experiment resulted in 1% decreased sales
* Google - Performance improvement impact on distinct queries, revenue, clicks, satisfaction and time-to-click


### **7. Microsoft Malware Reduction**

* Microsft overrode the basic routines that modify the DOM (Document Object Model) to allow only limited modifications from trusted sources on the search results page. Thus, prevent malware from polluting result page with ad pop-ups
* Results showed improvements to all key metrics - success rate, time to success, sessions per user, churn rate, revenue and page load time


### **8. Amazon Backend Changes to Recommendation Algorithm**

* Before - "People who bought item X bought item Y" & "People who searched for item X bought item Y"
* After - "People who viewed item X bought item Y" & "People who viewed item X viewed item Y"
* What was broken? - Example: Amazon search results for the 24 was showing poor results like 24-inch towel bar and 24-Italian songs instead of 24-TV show.


_________________________________________________________________________________________________________________________________________________________________________________

## <ins>**What's a multi-arm bandit?:**</ins> 
A multi-armed bandit is a type of experiment where the experiment traffic allocation can be dynamically updated as the experiment progresses. For example, we can take a fresh look at the experiment every hour to see how each of the variants has performed, and we can adjust the fraction of traffic that each variant receives. A variant that appaers to be doing well gets more traffic and a varaint that is underperforming gets less.






