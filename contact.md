---
layout: page
title: Contact
permalink: /contact/
---

# Easiest way

Send an e-mail to <a href="mailto:{{ site.email }}">{{ site.email }}</a>

# Open a FogBugz case

For defect reports, feature suggestions and general feedback, you can [create a new case in our FogBugz instance][sn-fogbugz].

# Encrypted

If you need to submit sensitive or confidential information over an insecure channel (such as when reporting a **security vulnerability** via e-mail), please encrypt your message and/or attachments using our **[PGP key][public-key]**:

**ID**
: 6ADC6845

**Type**
: RSA

**Size**
: 4096-bit

**Fingerprint**
: E2F1 E492 1C9C 369C 6CBF E393 E9F0 4520 6ADC 6845

Download the [Public PGP key][public-key]


## Quick PGP tutorial
<ol>
    <li>
        Install <code>gnupg</code>.  It's even available for Cygwin.  If you want to use a GUI, there's <a href="http://gpg4win.org/">Gpg4win</a> for Windows and <a href="https://gpgtools.org/">GPG Suite</a> for OS X.
    </li>
    <li>
        Download <a href="softwareninjas-public-pgp.key">softwareninjas-public-pgp.key</a>
    </li>
    <li>
        Import our public key in your store: <br />
        <code>gpg --import ~/Downloads/softwareninjas-public-pgp.key</code>
        <br />
        This will generate output like the following (notice the <em>key ID</em> should match the value above):
<pre>gpg: WARNING: using insecure memory!
gpg: please see http://www.gnupg.org/documentation/faqs.html for more information
gpg: /home/oli/.gnupg/trustdb.gpg: trustdb created
gpg: key 6ADC6845: public key "Software Ninjas (Signing and encryption) <info@softwareninjas.ca>" imported
gpg: Total number processed: 1
gpg:               imported: 1  (RSA: 1)</pre>
    </li>
    <li>
        (Optional) Verify the key fingerprint.
        <ol>
            <li>
                <code>gpg --edit-key info@softwareninjas.ca</code>
            </li>
            <li>
                <code>fpr</code>
                <br />
                This will generate output like the following (notice the <em>fingerprint</em> should match the value above):
                <pre>pub   4096R/6ADC6845 2014-07-20 Software Ninjas (Signing and encryption) &lt;info@softwareninjas.ca&gt;
 Primary key fingerprint: E2F1 E492 1C9C 369C 6CBF  E393 E9F0 4520 6ADC 6845
</pre>
            </li>
            <li>
                Compare the fingerprint with the value above.
            </li>
            <li>
                <code>quit</code>
            </li>
        </ol>
    </li>
    <li>
        Now we can encrypt <code>filename.ext</code> to create <code>filename.ext.gpg</code>: <br />
        <code>gpg --recipient info@softwareninjas.ca --out filename.ext.gpg --encrypt filename.ext</code>
        <br />
        You may get a warning that there is no assurance the key belongs to us.  Depending on your level of paranoia, you may wish to first contact us through another channel to verify the key's fingerprint.
    </li>
    <li>Attach <code>filename.ext.gpg</code> to an e-mail sent to <a href="mailto:info@softwareninjas.ca">info@softwareninjas.ca</a></li>
</ol>

[public-key]: /softwareninjas-public-pgp.key
[sn-fogbugz]: https://softwareninjas.fogbugz.com/default.asp?pg=pgPublicEdit
