.. _opencase:

Open Case
============

The goal of this page is to select variants and create annotations going into the final report.

Any change on the page is saved every 2 minutes or by clicking the save button at the top right corner in the toolbar.

Toolbar menu and buttons
------------------------
.. image:: img/opencase/menu_and_buttons.png


Patient Details
---------------

All cases need an **OncoTree Diagnosis** value. You can open Oncotree or Lookup Portal by using the two buttons next to the text field.

.. image:: img/opencase/oncotree.png
   :width: 400

Case Notes
----------

You can write any notes about the case that don't fit into a standard annotation.

Variant Tables (SNP, CNV, FUSION)
-------------------------------------------------------

Click on each tab to display the corresponding variants.

The **Flags** column indicates that a variant has failed or passed QC, has annotations (|mdaAnnotation| from MD Anderson, |utswAnnotation| from UTSW),
or has some warnings such as being a common variant.

.. |mdaAnnotation| image:: img/opencase/mda_annotation.png 
   :width: 20

.. |utswAnnotation| image:: img/opencase/utsw_annotation.png 
   :width: 20

The variant tables show all variants in the case VCFs, 
inclucing variants that failed our quality metrics.
To narrow down the list of variants, click on **Advanced Filtering** and the **Filters** menu will open.

.. image:: img/opencase/advanced_filtering_overview.png

Here you can filter on any field available in the variant table.

For instance, click on **Pass QC** and then click **Refresh**

.. image:: img/opencase/advanced_filtering_buttons.png
   :width: 600

More options are available when clicking on |filters| **Filters**. 
You can save filters for later use or load predefined gene sets.

More information on creating your own gene sets here: :ref:`annotations`.


.. |filters| image:: img/opencase/filters.png 
   :width: 80


.. image:: img/opencase/advanced_filtering_gene_sets.png
   :width: 600

To explore a variant details, 
click on the magnifying glass next to the variants position |variantdetails|

.. |variantdetails| image:: img/opencase/location_variant_details.png
   :width: 150



Variant Details (Annotations)
-----------------------------

This page shows more detailed information about a variant (SNP, CNV or Fusion).
You can browse existing annotations, create new ones see other transcripts and
explore external tools and databases such as IGV, gnomAD, Cosmic.

Some features are specific to the variant type such as the CNV chart.

If you think this variant should go into the report, click the **SELECT VARIANT** button.
To go into the report, a variant needs tiered annotations. More information here: `MDA and UTSW Annotations`_


Toolbar menu and buttons
^^^^^^^^^^^^^^^^^^^^^^^^

.. image:: img/opencase/variant_details_menu_and_buttons.png

Variant Details Panel (SNP)
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Shows all data available in the variant table row. And provide links to external tools.

.. image:: img/opencase/variant_details_panel.png

Variant Details Panel (CNV)
^^^^^^^^^^^^^^^^^^^^^^^^^^^

When opening a CNV, you can display a chart of the chromosome containing the CNV and create a new CNV by zooming in to the desired location.

You can zoom in on a particular location in the chart by dragging an area with your mouse. To zoom out, right-click to open a contextual menu
or click on the Reset Zoom button |reset_zoom|

.. |reset_zoom| image:: img/opencase/cnv_zoom_out.png
   :width: 100

.. image:: img/opencase/cnv_chart.png

Transcripts (SNP)
^^^^^^^^^^^^^^^^^

If you think the canonical transcript is not the correct one, select an alternate transcript from the **Other VCF Annotations** table.

.. image:: img/opencase/change_transcript.png

MDA and UTSW Annotations
^^^^^^^^^^^^^^^^^^^^^^^^

Other users may already have created annotations for a variant or a gene.

Annotations have a scope which allows to apply this annotations to other genes or variants. Annotations can also be limited to a case or a diagnosis.
This means that creating a gene level annotation will make the annotation visible to any variant in that gene for any case in Answer.

Click on **ADD/EDIT** to create new annotations or edit existing ones. You can only edit annotations you have created.

.. _opencase_create:

Create/Edit Annotations
^^^^^^^^^^^^^^^^^^^^^^^

Annotations are specific to the type of variant (SNP, CNV or Fusion) but they share general principles such as a scope.
An orange background indicates that you are in **edit** mode as opposed to just **view** mode.

The scope determines where the annotation applies to other cases/genes/variants/diagnosis. 
By changing the scope you can determine if an annotation should be visible for any variant in the current gene for instance (**Gene Specific**).
Or only for the current mutation (**Gene Specific** + **Variant Specific**)
Or only for the current mutation in the current case (**Case Specific** + **Gene Specific** + **Variant Specific**)

You can create regular annotations or clinical trials. Different fields are required depending on the annotation and variant type so the **SAVE / UPDATE** button might 
be disabled until all requirements are met. You can always go back and change you annotations so feel free to explore the different menus and options. Tooltips will guide you
through the buttons and drop down functions. 

You can create multiple annotations or trials by clicking |addAnnotationButtons| multiple times.

**Don't forget to save your work.** Autosave does not apply to creating/editing annotations.

.. |addAnnotationButtons| image:: img/opencase/add_annotation_buttons.png
   :width: 250

Once you close the panel. The new annotation cards will be displayed in the **UTSW Annotations** panel.

.. image:: img/opencase/annotation_cards.png

To include these annotations to the report, click **SELECT VARIANT** AND toggle each annotation card that you want included.
To be valid for reporting, at least one card needs a tier. The highest tier of the selected card will determine the tier of variant in the report.

You can close the window or click **PREV. VARIANT** or **NEXT VARIANT** to open other variants.

Review Selected variants
------------------------

Once you have select variants and created annotations that should go into the report, click on **Review Variant Selected** to get a list
of the variants that will go into the report.

Depending on your role, you can mark the case as:
- Send variants to MD Anderson: MD Anderson will send Answer annotations and clinical trials matching their database
- Ready for review: a reviewer will get an email to check that the appropriate variants are selected and make/select new annotations if needed 
- Ready for report: the reviewer informs that the annotations are ready and a report can be created

You can change the selection of variants by opening the **Variant Details** for each row in the tables.







