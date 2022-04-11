# Beta-Release of PK-Sim 11 and MoBi 11
Dear OSP users, 

We are happy to announce that the new Version 11 of PK-Sim and MoBi is now available for beta-testing. The beta-test phase will last until the **end of April**.
The goal of the beta release is to give you an opportunity to test the new features and to let us know if you have any problems or feedback regarding the new implementation.

## How can you test the new features?
You can use the *portable versions* of PK-Sim and MoBi  (download links below). The portable versions do not require installation and can be used in parallel to the official OSP Suite 9.

Your feedback on the new features is highly welcome.

**Important**: The beta-test versions are not final releases of the software packages: please use them for testing purposes only, but not for productive work.

## Downloads:

- [PK-Sim 11 beta portable](http://pk-sim-portable.open-systems-pharmacology.org)

- [MoBi 11 beta portable](http://mobi-portable.open-systems-pharmacology.org)

## New features

### Creating individuals and populations with CKD (Chronic Kidney Disease)

Already in version 10 of the software it was possible to use predefined CKD templates (based on the publication [Malik PRV, Yeung CHT, Advani U, Dije S, Edginton AN. A Physiological Approach to Pharmacokinetics in Chronic Kidney Disease. J Clin Pharmacol 2020. 60 Suppl 1: S52-S62. doi: 10.1002/jcph.1713](https://accp1.onlinelibrary.wiley.com/doi/full/10.1002/jcph.1713)).
However, an end user could not define individuals/populations with any covariates (weight, height, ...) by himself.
This flexibility is now offered with PK-Sim version 11.

When creating an individual, a new option **"Disease State"** is provided, which allows a selection between _Healthy_ and diseased individuals.
<p align="center">
<img width="800" src="https://user-images.githubusercontent.com/25061876/162768013-1c1b7ab9-e980-4d67-ba3c-abbd36630bdb.png">
</p>

For the details s. the [documentation](https://docs.open-systems-pharmacology.org/v/v11/working-with-pk-sim/pk-sim-documentation/pk-sim-creating-individuals#disease-state) and the original publication by Malik et al.



### Protein expressions as standalone building block
Till PK-Sim version 10 protein expression profiles could only be created within an individual or a population.
Starting with the version 11, protein expressions can be created independently (like all other building blocks) and thus can be **reused** in different individuals/populations.
<p align="center">
<img src="https://881660647-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FewOAYfFFhObyan6wZQs0%2Fuploads%2Fgit-blob-969bf4fe9c3d8a2534a34cb1a5a4864584c604c6%2FCreateExpressionProfile.png?alt=media">
<img src="https://user-images.githubusercontent.com/25061876/162777774-ea5c00c7-7c9f-42a5-b411-8d81be0e3ec0.png">
</p>


### XXX

## Fixed issues and Improvements

### PK-Sim



### MoBi



### PK-Sim and MoBi

