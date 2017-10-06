# Contact

- [General](#general)
- [Sending your email Address Privately](#sending-your-email-address-privately)
- [Double-Blind](#double-blind)

----------
## General

I use git primarily for archive repositories.  If you are interested in
collaborating, or have a suggestion, or most importantly, have found an
error or omission, I am eager to hear from you.

#### Utopia

In an ideal world, I would simply publish my email address.  Responsible
people desiring to communicate would just send me an email, and I would
be untroubled by nonsense that wastes my time.

#### Reality

Email is completely broken.  In order to thwart marketers, phishers,
spam artists, and sundry crackpots, I do not publish my email
address. That, however, is insufficient.

Believe it or not, there are actually instructions available online
showing people who know nothing about `git` how to harvest the email
addresses that are part of every repository.  The people at `GitHub`, in
their infinite wisdom, provide a remedy.  By default, a new account is
set up to keep email private.  There is also an option that prevents me
from accidentally pushing my email to a repository, and I have selected
that option.

Additionally, my '`.gitconfig`' file contains the line:

      email = ruminations@users.noreply.github.com

and it is the email address of record in all my repositories.  Moreover,
`GitHub` uses the same address for account related notifications.  Sending
an email to that address results in a notice that your missive is
undeliverable.  I will remain blissfully unaware of the contact attempt,
and hence untroubled by delinquents.

People who know something about `git` know how to contact me anyway.  They
simply raise an issue on one of my repositories.  `GitHub` forwards the
issue, and if I see fit, I respond.  This small barrier is apparently
beyond the ken of the social parasites.

#### An Alternate Solution

Given the nature of my interests, there are those who know nothing about
`git` who may have a legitimate communication to send.  Here is how you do
that:

1. Create a throw away `GitHub` account.
2. Raise an issue on this repository.
3. After I reply, be courteous, and delete your throw away account:
   * Go to the user settings page.
   * Select account management in the side bar.
   * Click on `delete account`.

**NOTE**: `GitHub`, in its [infinite stupidity](https://stackoverflow.com/questions/3081521/how-to-completely-remove-an-issue-from-github),
has made individual issues undeletable.  For this reason, periodically,
I will delete this entire repository and recreate it, sans historical
issues.  It is for this reason that my prefered communication channel is
'Double-Blind' - see the section below.

If your communication pertains to a specific repository, by all means
raise the issue on that repository.  As should be obvious to any
intelligent reader, any form of social hustle is unwelcome.  That
specifically includes employment recruiters, media employees, and
individuals addicted to fatuous social media outlets.

#### Defects in the Alternate Solution

There are two problems with that simplistic solution, detailed here.

##### A: Coercive Participation

My solution forces you to join `GitHub`.  I understand all too well how
odious that is.  Social media outlets use that tactic extensively to expand
their user base, often denying even casual perusal of content to outsiders.
It is for this reason I absolutely refuse to participate in social media.

There are differences, however, in my coercive requirement:

1. It is not the provider (`GitHub`) imposing the coercion - it is me.
2. Unlike social media, your participation is guaranteed to result in a
   successful contact, although it is not guaranteed to produce a reply.
3. Unlike social media, the path to successful removal of participation
   clearly exists apriori - you will be able to easily remove your
   account by following the instructions above.
4. Unlike social media, you will not forever-after be tracked all over
   the internet.
5. Unlike social media, you will not forever-after be targeted by all
   manner of rubbish that wastes your valuable time, network bandwidth,
   and computing resources.

Moreover, for some inexplicable reason, coercive participation does not
seem to be a barrier for the great majority of people.  If you are
willing to accept the privacy intrusions of social media, you should be
more than willing to surmount the small barrier to communication I have
imposed.  If you are more like me, you can see that this barrier is
miniscule in comparison to that routinely imposed by social media.

##### B: Issues are Publicly Viewable

This is a bigger problem.  If I don't want my email address visible, why
should I expect you to make your's public?  Indeed.  There is a solution
to that.  Follow the instructions in the next section.

---------------------------------------
## Sending your email Address Privately

Anyone seriously using `git` is familiar with `ssh`.  If you already have
a `GitHub` account, you doubtless connect using `ssh` and have uploaded one
or more public keys.  The instructions here show you how to raise an issue
whose content is your email address encrypted with my public key.

As a consequence, although the issue is public, I am the only one who can
decrypt and gain access to your address.

For your convenience, the file '`id_rsa.pub.pem`' in this repository
contains my public key in the format necessary to follow these
instructions.  The file '`secure_communication.txt`' gives a more detailed
tutorial for those who might like to use this method in other contexts.

1. Click on the `.pem` file in this repository, view it in raw mode, and
   copy the text into a file on your local machine in some convenient place.

2. Open a terminal in that directory and issue the command chain:

       echo "user@example.org" | \
       openssl rsautl -encrypt -pubin -inkey id_rsa.pub.pem | \
       base64 # > cipher.txt

   where '`\`' is the line continuation character and may be omitted if you
   prefer to pack everything into one command line.  In the first line
   replace '`user@example.org`' with your email address and a short message
   (retain the double quotes).  In the second line, '`id_rsa.pub.pem`' is
   the local file you put my public key into, and may be named anything.
   The name here is the name I used.

Loose functionality is:

1. `echo` creates a text stream feeding through a pipe to
2. `openssl` that converts it to an encrypted stream feeding a pipe to
3. `base64` that converts it to a printable character stream.

Optionally, you may funnel that text into a file by removing the
comment command '`#`'.  Or you can use it as is and copy and paste the
output printed on the terminal into the issue you raise.  That text
will look something like:

    dNQvt1WlAQtffemJ33a63R29GB38vOZkfCkVX+cHsXG45jKodGqlcV760HHhK8aTmenAIHiiYYS/
    W/v79sKiVqJyiwDoL78bHmg+2CgPHd+ag0Kmlb5G8UlRByDLo3EvRLfTb8p+m88XZtbx7O6oHkrM
    ZCL/rVuhrBfp4C32xHUWGeMGtsVwH0lCQdRwME79DUFeO9QSKdElh8Ux+X+GABWovys+WPZ/wCri
    OkstYvZACBwwUFiGsiiWBw/2VWoX6OAWs2H8OybZs5Gi/Q2b0vJ+g3mKbvkXXd7YFXXAIn11oSL7
    jGdqBrCs6D+6SnC90NPbmJsFINlZ3qn+3DKoE4LF/B67fbWt9OXK68gmdCKCT7RBYFYLtoPDiD2I
    sMRi/81o8foY4ZUFWuOnF5ntaAEhtMdGBSgMJRHnQxC2cwmRWwuB8TbMiSUW5PsmURnK8s7dzHJQ
    ZnAf3RL5LWcaBKC6Fi5y/40DWTzIw4grXIVhjIdB04ZhnZucu7E0MOYK3JFW3VjYospj2d8c1fy4
    A6sQvTriutHOD2HurXxlRJiSN/VRqReQgebIxS/mzSnqfBJTaKAXWw0a60+Cf0nfOjTEbP/UYK/l
    vcEhYcvThK7iyKjABSYsFVrsnPkILBcMOZrzepX0MZ4OQFcAKPeQJs2a3HoBrTua850VFWpAeeE=

Since I use a 4096 bit key, the method is limited to 500 character
messages, more or less, depending on the actual size of the public key
that `ssh-keygen` created.  In my case, the limit is 500 characters.

That's all there is to it!

---------------
## Double-Blind

If you like, in lieu of your email address, you may send the `url` of your
`GitHub` contact repository similar to this one.  I can then post an encrypted
reply and neither of us will ever know the other's email address (assuming
you have elected to keep your `GitHub` contact address private).

Note that this is **_not_** anonymous.  `GitHub` knows your email address
and mine and also logs the ip addresses of transaction origins under your
account settings security tab.

The process merely ensures privacy - there is no reason for the plain text
of communications to ever leave the local machines of the communicants,
assuming they trust one another's integrity, and personal email addresses
remain as secure as the privacy provisions offered by `GitHub`.
