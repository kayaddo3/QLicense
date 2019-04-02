# QLicense
A Ready To Use Software Licensing Solution in C#

I had a application having feature 1, 2 and 3,  and I want user to pay for each feature they like instead of paying for the whole package.
So I designed a license solution to make this possible.
Current Solution

1) My application launches and finds itself not activated
 2) It displays the activiation form and show the current device UID for purchasing a license
 3) User shall give this device UID to our vendor to purchase the license, via either mail or phone.

4) At our vendor side, there is a license issuer program to issue the license based on the device UID and those features the user bought.
5) After license is generated, vendor shall paste the license string into a text file or mail to our user for activation.

6) User use paste the license string into the activiation form to activate the application.

Well, if this make you interested, please read on.

The highlights of this solution is:

digital signature technology is used to protect the license file
XML based license file allows it to contain rich information needed by the application
support both single license mode and volume license mode.
for single license mode, PC's unique key is generated based on PC's hardware. And BASE36 algorithm is used to generate the unique key for easier usage.
As I learnt, the key concept of such a license solution has been introduced years ago, even there are similar articles on CodeProject as well. However, it seems to be no ready-to-use solution or library out there. So it is a chance for me to do it!
Background

I was working on a project that is a system having many key features, which are expected to be actived or deactived based on the license provided. Boses want the feature on/off mechanism of the licensing system to be highly flexible, so the idea of pre-defined different editions is not suitable for this purpose.

The benefits is end user can just pay for those feature he/she want. E.g., user A can only pay for feature A, B & C; while user B only want feature A & C, and user C may only pay for feature B.

A good idea is to put those active features into a XML list and use this list as the license file. However, the next question is how to protect this license file since it is juat a plain text XML. Finally the digital signature solution answers the question.
