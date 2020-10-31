---
title: 'Privacy and Security Series, Part I: Password Managers'
date: '2019-02-11T07:50:00.007Z'
layout: post
---

I've been wanting to write a blog series on personal internet security for a while now. There's never a bad time to talk about security, and I've got some interesting topics ranging from protecting your privacy to protecting your identity and your character. We might casually think of security breaches and leaks as happening only to large, faceless organizations, but that's simply not true. There are steps you can and should take to secure your privacy. The first and most important step is to get a password manager. Let's begin.

## 2019: Year of the Password Manager

Seriously, it's 2019 and if you aren't using a password manager, it's my humble opinion that you're setting yourself up for a [_bag of hurt_](https://www.macworld.com/article/1136079/bluray.html). Security breaches happen every day, some detected and others not. You must assume any credential to any web service could be leaked. To mitigate this risk, you need to:

- Use random, complicated passwords
- Never reuse a password

By doing these two things, any leaked credentials can't be used to access other accounts. How do you accomplish them? Use a password manager. Recent changes in Apple's iOS and Google's Android have made it easier than ever to use password managers on your phone as well. You can read more about password managers [here](https://techcrunch.com/2018/12/25/cybersecurity-101-guide-password-manager/), but really you should stop questioning it. Basically if you use the internet, you are at risk.

### How to do it right

It's not enough to just store your passwords in a password manager. Here's how to properly use a password manager:

1. **Your master password must be completely unique.**

   It can't be related to anything else. There can be no chance of it leaking because it can only live in your head. It can't be easy for someone to figure out. It can't be birthdays, it can't be pet names, it can't be family names.

   One thing to note: passwords made up of words and phrases can actually be stronger than some passwords with common numbers or symbols. Have you heard of "[correct horse battery staple](https://xkcd.com/936/)"?

2. **Always generate passwords with as much randomness as possible.**

   Every website should get its own unique password. The more complicated it looks, the better. You're not going to remember it, your password manager is!

   You'll often find certain websites, like government, medical, and finance websites, that can't support a wide range of characters for the password, or can't support a long password. That's shitty (compliance and regulation lags behind actual best practices), but a password manager will help you make the best of this situation. A good password manager will have an entropy meter which will help you determine the strongest password you can fit into limited password requirements.

   Now of course, whenever you CAN generate complicated passwords, you should. Most modern websites will support fairly long and complex alphanumeric passwords.

3. **Audit your passwords.**

   As we talked about, Leaks Happen™. So, you need to be notified when your passwords have leaked online. First, go to [haveibeenpwned.com](http://haveibeenpwned.com) to check your different email addresses, and then sign up for their email alerts. Have you been pwned? (Me too, there's no shame in it. It's just random! Really, if you've used the internet, you've probably been pwned.) If so, it's time to change some passwords.

   Good password manager apps will have functionality built in to locate weak passwords. You should change identified weak passwords immediately.

   You also can never have a duplicate password. Having a duplicate password is a really bad scenario, because then a single leak leaves you vulnerable in multiple places. Password managers generally will alert you to and discourage you from using duplicate passwords.

   Also, look for your credit providers to offer email alerts. There are some vendors that will search parts of the dark web to look for your information in leaks.

   Also also, were you part of the Marriott Leak? If so, sign up for the identity protection services they're paying for. It's the least you could do.

   And don't ever use a non-randomized password for anything ever again.

4. **Don't answer security questions truthfully.**

   Security questions are bad. Do you know how easy it is for someone to figure out your birthday, your mom's maiden name, and/or your pet's name? These security questions are the _weakest_ form of security I can think of. Don't give real answers.

   Instead, give fake answers, or even better, put random passwords in for each question. Note that some websites won't accept highly-complex answers to security questions. That's okay, just make sure to watch the entropy meter of your password manager to generate the most secure answers possible.

   Now, anytime someone might try to reset your password or otherwise circumvent normal authentication flow, they'll be met with questions that have nonsense password answers.

   > Q: What is your mother's maiden name?
   >
   > A: "9T9.FE#54R98416B"

   Such a beautiful name.

5. **Get an app everywhere you need it.**

   It seems important to say this. If you're setting up a password manager properly, you're no longer going to know any passwords except your master password.

   That means you need to sync up those passwords with any phones, tablets, or other computers that you use. Being locked out of your Google account because you're away from your computer isn't productive.

   Most password manager apps will cloud-sync your passwords in a premium offering, either on a subscription or a one-time purchase. Cloud syncing is secure because your password wallet is encrypted with your master password— it's a waste of resources for an adversary to try to brute-force decrypt your password wallet unless you're someone ultra-important and believe state-sponsored attackers are targeting you. You can also use an offline password manager like KeePass and sync the passwords manually, though this is wildly inconvenient.

   Oh, and this includes browser extensions. All good password managers should have functional extensions that make it a breeze to use your secure passwords as you browse.

6. **Be diligent.**

   Commit to using your password manager.

   If you have a lot of accounts on many websites, you're going to quickly realize it's a lot of effort to set up the password manager. As you log in to more sites and save those passwords in your app, you'll have to go back and audit again. Most passwords will need changed completely (to a new, secure one), some sites will have outdated URLs, login flows, etc. Be focused about taking care of this one day at a time, because it's easier to handle this as it arises.

   A password manager also allows you to be cognizant about the accounts you have. Every once in a while I like to go through my password manager just to see what accounts I have open that I no longer use. It's always great to reduce the attack surface.

## Next Time

Having secure passwords is just one part of a sound internet security strategy. Stay tuned for Part 2 of this series, where we'll talk about the next tool in your arsenal: two-factor authentication.

Thanks for reading!
