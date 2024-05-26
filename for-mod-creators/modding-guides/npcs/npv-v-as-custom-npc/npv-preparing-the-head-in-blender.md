---
description: 'Step 1: How to generate your V''s custom head mesh'
---

# NPV: Preparing the head in Blender

## **Summary**

**Published by @manavortex, May 13 2023**\
**Last documented update: Jan 04 2024**

This page is a part of the [NPV guide](./). It will show you how to create your V's **head** in Blender. If you want to load your head back into Cyberpunk, note that you aren't changing anything in the files itself — that will come in [npv-creating-a-custom-npc.md](npv-creating-a-custom-npc.md "mention").&#x20;

We will not be dealing with the body, this is part of the next section as well.

If you want a 3d model, you probably know what you're doing; in that case, make sure to run the script and get the shape right, then go wild.

### Prerequisites

* [ ] You have downloaded the prepared Wolvenkit Project from [Nexus](https://www.nexusmods.com/cyberpunk2077/mods/8328)
* [ ] You have [Blender](https://www.blender.org/download/) installed \
  _(confirmed working on 3.5.1, 3.6 and 4.0)_
* [ ] You have the Wolvenkit Blender Plugin (you won't be able to export otherwise). Check [installing-the-wolvenkit-blender-plugin.md](../../../modding-tools/wolvenkit-blender-io-suite/installing-the-wolvenkit-blender-plugin.md "mention") if you don't.

In this section, we will be moving/deleting files. You can complete these steps in Wolvenkit or in the Windows File Explorer.

{% hint style="warning" %}
It's important that you leave the file structure **as it is**. Moving or renaming files will confuse Wolvenkit and break the example project.&#x20;

The final section of [npv-creating-a-custom-npc.md](npv-creating-a-custom-npc.md "mention") tells you how to safely move files.
{% endhint %}

## Step 1: Getting head

1. Open the `head` folder in your project's `archive` section.
   1. **Optional:** Be confused and/or panic about why there are over 9000 files.list
   2.

       <figure><img src="../../../../.gitbook/assets/3 head folder.png" alt=""><figcaption></figcaption></figure>
2. Look into the `head/morphtargets` folder
   1. **Optional:** Be confused and/or panic about why there are over 9000 files **again**.&#x20;
   2.

       <figure><img src="../../../../.gitbook/assets/4 scroll down to find morphtargets folder.png" alt=""><figcaption></figcaption></figure>
3. Delete all those files that you aren't using (read on as for how)

{% hint style="info" %}
**It's too many of them!**

True! That's because I included **all** options for any given V. But don't worry: after you have deleted the ones that you won't be using, you should be left with a maximum of 13 `.morphtarget` files for female V and 14 files for male V.&#x20;
{% endhint %}

I have included all meshes and morphtargets from the game files. We'll now thin out the options, deleting those parts that your NPV won't be using.

### Deleting unused files: the convenient option

{% hint style="success" %}
The best and most convenient tool for the job is [NoraLee's NPV picker](https://noraleedoes.neocities.org/npv/npv\_part\_picker). It will give you a list of files that you need to keep.&#x20;

The list will give you a number of **Source Mesh** entries like `h0_000_pwa_c__basehead.mesh`.&#x20;

You need to keep these files inside the `head` folder and the `.morphtarget` file in the subfolder `morphtargets`. If you want to understand why, keep reading; otherwise, you can proceed to [Deleting Files](npv-preparing-the-head-in-blender.md#deleting-files).
{% endhint %}

<details>

<summary>What the actual fuck are all those files?</summary>

#### Meshes vs Morphtargets

The `.mesh` files are the 3d files making up your NPV's head. I've taken them from the game files and prepared them for you (by making them use the player animations and -expressions).&#x20;

The `.morphtarget` files are the character creator options (a direct game export). You can safely overwrite them with the most recent version by searching Wolvenkit for the file name  – you need to put it into the correct folder, though, or it won't be picked up by the scripts.

We only need the .morphtargets to generate the actual meshes by duplicating the character creator process.

#### Okay, and all those numbers?

The different variants in the character creator correspond to the different meshes. For example, if you select cyberware 3 in the character creator, the mesh that will get loaded is `cyberware_03`. Not so difficult, is it?

To learn what the prefixes mean, check [#head-file-prefixes](../../../references-lists-and-overviews/cheat-sheet-head/#head-file-prefixes "mention").

</details>

### Finding the right piercing

{% hint style="info" %}
If your V isn't using any piercings, you can skip this step and go directly to [Deleting Files](npv-preparing-the-head-in-blender.md#deleting-files).
{% endhint %}

In the files, you will see four files for jewelry:&#x20;

```
tutorial\npv\your_female_character\head\i1_000_pwa_c__basehead_earring_01.mesh
tutorial\npv\your_female_character\head\i1_000_pwa_c__basehead_earring_02.mesh
tutorial\npv\your_female_character\head\i1_000_pwa_c__basehead_earring_03.mesh
tutorial\npv\your_female_character\head\i1_000_pwa_c__basehead_earring_04.mesh
```

… none of which is your V's exact piercings. Instead, there are full sets of jewelry, most of which will be **hidden**.

You have to look at the meshes and find the file that **includes your set of piercings**. We will delete the ones you don't need later.

### Deleting files

{% hint style="success" %}
Number in file name <=> Number in character creator
{% endhint %}

{% hint style="info" %}
Do not delete any files if you're [editing the player head](../a-new-head-for-v.md) (Ignore this hint if you aren't).
{% endhint %}

Many of the files are **variants** and your V will be using **one or none of them.** That means you have a bunch of files to delete.&#x20;

* If you have chosen [the convenient option](npv-preparing-the-head-in-blender.md#the-convenient-option), you should already have a list of files that you need to keep.&#x20;
* Otherwise, you need to refer to [#what-the-actual-fuck-are-all-those-files](npv-preparing-the-head-in-blender.md#what-the-actual-fuck-are-all-those-files "mention") and use the table below for some oversight.

{% hint style="warning" %}
When deleting files that you aren't using, make sure to remove both the `.mesh` file in the `head` folder and the `.morphtarget` file in the `head/morphtargets` folder, both in the [archive](https://app.gitbook.com/s/-MP\_ozZVx2gRZUPXkd4r/wolvenkit-app/usage/wolvenkit-projects#archive) and the [raw](https://app.gitbook.com/s/-MP\_ozZVx2gRZUPXkd4r/wolvenkit-app/editor/project-explorer#raw) section.
{% endhint %}

The following table will show you examples on what to **keep** (as in, you **delete everything else**):

<table><thead><tr><th width="247">Body gender/variant</th><th>Files not to delete from variants</th></tr></thead><tbody><tr><td>female V, cyberware 03</td><td><pre><code><strong>tutorial\npv\your_female_character\head\hx_000_pwa_c__basehead_cyberware_03.mesh
</strong>tutorial\npv\your_female_character\head\morphtargets\hx_000_pwa__morphs_cyberware_03.morphtarget
</code></pre></td></tr><tr><td>male V, scars 01</td><td><pre><code>tutorial\npv\your_male_character\head\hx_000_pma_c__basehead_scars_01.mesh
tutorial\npv\your_male_character\head\morphtargets\hx_000_pma__morphs_scars_01.morphtarget
</code></pre></td></tr><tr><td>male V, big beard</td><td><pre><code>tutorial\npv\your_male_character\head\hx_000_pma_c__basehead_scars_01.mesh
tutorial\npv\your_male_character\head\hb_000_pma_c__basehead_big_beard.mesh
</code></pre></td></tr><tr><td>female V, tattoo 09</td><td><pre><code>tutorial\npv\your_female_character\head\hx_000_pwa_c__basehead_tattoo_09.mesh
tutorial\npv\your_female_character\head\morphtargets\hx_000_pwa__morphs_tattoo_09.morphtarget
</code></pre></td></tr><tr><td>male V, no earring</td><td><p>Files to delete (0* means "01 - 04"):</p><pre><code>tutorial\npv\your_male_character\head\i1_000_pma_c__basehead_earring_0*.mesh
tutorial\npv\your_male_character\head\morphtargets\i1_000_pma__morphs_earring_0*.morphtarget
</code></pre></td></tr></tbody></table>

#### Expected result

After deletions, both `head` and `head/morphtargets` should hold only the files that your V is actually using.&#x20;

For a list, see the [table above](npv-preparing-the-head-in-blender.md#okay-and-all-those-numbers).

Once you're done, you should have between 4 and 13/14 files:

<table data-header-hidden><thead><tr><th width="281"></th><th></th></tr></thead><tbody><tr><td>minimum number of files</td><td>4</td></tr><tr><td>maximum number of files</td><td><p>13 (female body gender)</p><p>14 (male body gender)</p></td></tr></tbody></table>

## Step 2: Exporting head

Now, we will export all `.morphtarget` files from Wolvenkit so that we can edit them **in Blender**.&#x20;

{% hint style="success" %}
You will complete most of these steps in Blender, only the import/export happen in Wolvenkit.
{% endhint %}

{% hint style="info" %}
If you run into any **errors**, check [#step-5-optional-troubleshooting](npv-preparing-the-head-in-blender.md#step-5-optional-troubleshooting "mention")
{% endhint %}

1.  Find the Export Tool (Tools -> Export)

    1. To filter, click into the empty row under "name" and write "`morphtarget`"
    2. Check the box in the header to select everything
    3. Click "Export Selected"



    <figure><img src="../../../../.gitbook/assets/npv_export_files.png" alt=""><figcaption><p>Export all your morphtargets. Mesh files will be auto-generated for you.</p></figcaption></figure>
2. Switch to your project's `raw` folder or Wolvenkit's `raw` perspective. You will find the entire file structure mirrored there.
3. In `head` folder, find the file `head_import.blend`. \
   This file is a **utility file** which will automatically import and export the files for you. For that reason, it needs to be in a certain relative path.

{% hint style="info" %}
If you have already changed your structure (by re-naming your folders), you need to make sure that `head_import.blend` is in the folder `head` right next to the folder `morphtargets.`
{% endhint %}

4. Open it in Blender. It will take you to the **scripting** perspective, where you'll see something like this:

<figure><img src="../../../../.gitbook/assets/npv_blender_00_import.png" alt=""><figcaption><p>Looks scary, but you don't have to do anything here!</p></figcaption></figure>

5. Press the **play ▶️▶**button.
6. The script will now import a bunch of armatures from the `morphtargets` folder. You will see them showing up in the topright corner (see the next screenshot under 7. for how it should look)
7. Switch to the next script in the file, but **don't run it yet**:

<figure><img src="../../../../.gitbook/assets/npv_blender_00_import_2.png" alt=""><figcaption><p>select "01_apply_shapekeys.py" from the dropdown menu</p></figcaption></figure>

{% hint style="info" %}
If you've been previously afraid of scripting: This is a good place to stop! :))
{% endhint %}

8. Find line 26 and following in the script, and alter the values to those of your V (which you get from **the character preset**, see [here](npv-preparing-the-head-in-blender.md#the-character-preset) for further explanation).&#x20;

<figure><img src="../../../../.gitbook/assets/npv_blender_01_apply_shapekeys.png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You don't need to select the eyebrows here, as those are "painted on" later via mesh appearance. The mesh only needs to have the right shape, which is what we're doing here.
{% endhint %}

9. After you've changed the values to those of your V, click the "play" button again. This will apply the morphs to your V's face:

<figure><img src="../../../../.gitbook/assets/npv_tutorial_before_after.png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
Some shapekeys don't correspond 1:1 with their numbers in the character creator. If a part of your shape is shaped subtly wrong or looks weird in the game, **undo** your changes (Ctrl+Z), add or subtract 1 from the corresponding shape key, and run the script again.
{% endhint %}

#### Can I have that with textures?

Yes, you absolutely can! Once you have imported everything back into Wolvenkit, you can re-export the `.mesh` files and use the [Wolvenkit Blender IO suite](../../../modding-tools/wolvenkit-blender-io-suite/) to import them with materials.

## Step 3: Importing head

{% hint style="info" %}
Unless you are editing original V, start by **deleting the morphtargets** from the template file — we don't need them anymore.

Remove the entire folder, both from `raw` and `archive`. From now on, it's meshes only!
{% endhint %}

### Exporting from Blender

Now that your head looks the way you want, it's time to run the final script, which will export your changed head to .glb for you:

<figure><img src="../../../../.gitbook/assets/npv_blender_03_export.png" alt=""><figcaption><p>Select and run it</p></figcaption></figure>

This will overwrite already existing files, leaving you with a set of import-ready mesh files.&#x20;

Now it's time to get them back into Wolvenkit.

1. Find the Import Tool (Tools -> Import Tool)
2. Click "Import All". You shouldn't see any errors.
3. You're done!

{% hint style="success" %}
At this point of the guide, you should see your NPV's head in Wolvenkit (re-select the mesh to refresh the preview).&#x20;
{% endhint %}

If the head mesh has **not changed**, you ran into a problem — check the Log View and/or make sure that you completed all steps in the right order. Especially **changing any paths** will break things.

## Step 4: Make sure that it works

Spawn your NPV and check that they look like they should.&#x20;

* If they do, proceed with [npv-creating-a-custom-npc.md](npv-creating-a-custom-npc.md "mention")
* If they don't, check [#step-5-optional-troubleshooting](npv-preparing-the-head-in-blender.md#step-5-optional-troubleshooting "mention")

## Step 5 (optional): Troubleshooting

Optimally, this process just runs with no hitches. However, during beta testing and troubleshooting, people ran into a few issues, so I'm listing them here.

### Blender won't export

You **need** to use the [wolvenkit-blender-io-suite](../../../modding-tools/wolvenkit-blender-io-suite/ "mention") for export. Make sure that it is installed and up-to-date.

### Blender script errors

You can check if Blender has run into errors by opening the **Blender console window** - from the menu, select Window -> Toggle System Console.&#x20;

As of December 2023, **any** script errors have been because the person encountering them has been using the wrong [Blender](https://www.blender.org/download/) version. You can see which version is currently running either [via UI](https://blenderartists.org/t/what-blender-version-am-i-using/1327264) or by checking the path in the system console window's title:&#x20;

<figure><img src="../../../../.gitbook/assets/npv_blender_version.png" alt=""><figcaption><p>This is using Blender 2.93, which is definitely not compatible.</p></figcaption></figure>

As of plugin version 1.5.5.1, you should have at least 4.0 installed.

### The piercings are in the wrong position!

The problem went away after the person having it upgraded Blender.&#x20;

### V was imported, but they're unsettlingly, subtly _wrong_

If you had the example project lying around for a very long time, please try and redownload it ([Nexus link](https://www.nexusmods.com/cyberpunk2077/mods/8328)), as the first version had been using an NPC animationgraph for facial expressions.

If that's not it, then you ran into the shapekey offset issue: some shapekeys don't correspond 1:1 with their numbers in the character creator. If a part of your shape is shaped wrong or looks weird in the game, **add or subtract 1** from the corresponding shape key, and run the script again.

