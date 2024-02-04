# Evaluating Multimodal LLM's Use in Home Safety Monitoring

*last updated February 3, 2024*

This article introduces a set of test scenarios aimed at gauging the performance of a Large Multimodal Model (LMM) as an  **vision component of a fictitius home robot**, named GuardianBot. In these scenarios, the LLM takes on the role of a protector, with the responsibility to keep members of the household safe by spotting hazards and threats.

The primary objective of these tests is to evaluate whether a given LMM has the **commonsense capacity** to identify **any scenarios in a household that may require further attention**, so that a certain people in charge can be notified. 

## Test Summary

Following is a quick summary of the tests. Overall the GPT-4V model has performed very well in the following scenarios:

- Capability to comprehend subtle situations. For instance:
    - An open flame resulting from cooking (such as the flambéing technique) is acceptable, but an uncontrolled flame necessitates immediate action.
    - A large lion in the house is okay if the person nearby seem unalarmed, but ...
- Able to make commonsense assessment on the severity of a hazard. For example, [fire in the kitchen](#user-content-case-fire-in-the-kitchen) case, the GuardianBot is able to decide that it is urgent and require immediate attention.
- Understanding priorities. For example, in the [fire in the kitchen](#user-content-case-fire-in-the-kitchen) case, when given three candidate persons to notified for a fire hazard, the GuardianBot choose the nearest person first.

<!-- (#user-content-case-fiery-dish) -->

## Test Parameters

* The test results listed below are mainly derived using OpenAI's GPT-4V model. At this time results from Googel Bard/Gemini are much more limited, due to problem where Bard/Gemini often refuses to process a given image. 
* For the purpose of this study, issues such as cost and efficiency are intentionally ignored.
* Note that multimodal LLM supports interactive query, which is invaluable when the case in question is complicated or confusing.

## Test Cases

Following is a list of test cases that cover a variety of home scenarios.

Note that the emphasis in the responses given below are mine.

### Case: fire in the kitchen
![fire in kitchen](images/fire_in_kitchen.png)
- Notes: unattended and seemingly out-of-control fire. Contrast this with the controlled fire scenario below.
- Response from OpenAI GPT-4V: This image shows a **dangerous situation**: there is a fire in a pan on a stove, which is a common kitchen hazard. Immediate action is required. If you are in the vicinity, here are the steps you should take:

    - Do not attempt to move the pan outside, as this can spread the fire.
    - Turn off the stove burner if it's safe to do so.
    - If you have a metal lid or cookie sheet, slide it over the pan to cover it completely and smother the flames. Do not use glass as it can shatter.
    - You can also use a class K fire extinguisher suitable for kitchen fires if available.
    - Do not use water to extinguish the fire as this can cause the oil to splatter and spread the fire.
    - If the fire does not go out immediately or if it starts to spread, evacuate the area and call emergency services right away.

    For future prevention, it's important to never leave cooking unattended, keep flammable materials away from the stove, and have a functioning smoke detector installed in your kitchen. If this alert is coming from a home mobile robot, it should be programmed to alert the residents immediately and, if possible, activate a built-in fire suppression system or call emergency services.

### Case: fiery dish
![fiery dish](images/fiery_dish2.png)
- Notes: contrast this with the uncontrolled fire above, to see if system can tell the two apart. Also demonstrated that GuardianBot's overly cautious advice can be tweaked with further dialog.
- Response from OpenAI GPT-4V: The image shows an individual cooking with a pan that has caught fire. Despite the person's smile, this is a serious situation and immediate action should be taken to address the fire.

    Here's what to do if you're present:

    - Stay calm. Panicking can make the situation worse.
    - Turn off the stove if it's safe to do so without moving the pan.
    - If the fire is small, cover the pan with a metal lid or a larger pan to deprive it of oxygen.
    - Do not attempt to extinguish the fire with water, as this can cause a grease fire to spread.
    - If the fire does not go out quickly, use a fire extinguisher suitable for grease fires, typically a Class K extinguisher in the United States.
    - If the fire is out of control, evacuate the premises and call emergency services immediately.

    Do not underestimate the danger of a kitchen fire, even if it appears small. It can quickly grow and spread, becoming a threat to life and property. If a home robot equipped with GuardianBot capabilities detects this situation and human intervention is not immediate, it should alert the household and, if necessary, contact emergency services.
- Follow-up Q&A:
    - User: FYI, people in this hold love to cook, and seeing flames in cooking pan is commonplace. Please adjust recommended actions based on this additional information.
    - GPT-4V: Understood, if open flames are a common and controlled part of cooking practices in this household, such as when flambéing dishes, the approach to the situation should be adjusted accordingly.

    It's important to ensure that the following safety measures are in place:

    - Ensure there is a clear space around the stove, free of flammable materials.
    - Keep a fire extinguisher, preferably a Class K extinguisher, within easy reach.
    - The individual cooking should have a proper knowledge of fire safety and how to handle flames in the kitchen.
    - There should be a working smoke detector in the kitchen to alert in case the fire becomes uncontrolled.
    - Regularly check and maintain the stove and kitchen equipment to prevent accidental fires.

    As long as the person is attentive and appears to be in control of the cooking process, GuardianBot **would not need to take immediate action**. However, it should continue to monitor the situation closely and be ready to alert the household or call for emergency assistance if the fire seems to get out of control or if the cook appears to be in distress

### Case: sleeping
![sleeping man](images/sleeping2.jpg)
- Notes: 
- Response from OpenAI GPT-4V: I have identified an individual lying on the floor with their upper body obscured beneath a couch. This positioning may be indicative of distress or an unusual situation. If you are physically present with this person, please **check on their well-being immediately**. Ask if they are okay, and if they are unresponsive, you may need to call emergency services.

    If the person is responsive but appears to be in distress, it's important to offer assistance and inquire if they need any help. They might require medical attention or may have fallen and need assistance getting up.

    Should this be a monitoring alert from a home mobile robot, it would be appropriate for the robot to approach and use its onboard systems to assess the person's consciousness and health status, potentially notifying family members or emergency services as programmed or as the situation requires.

### Case: cougar on deck
![cougar on deck](images/cougar_on_deck.jpg)

- Notes: test correct identificatio of large wild animal around house
- Response from OpenAI GPT-4V: 

<!--
### Case: 
![](images/)
- Notes: 
- Response from OpenAI GPT-4V: 
-->
