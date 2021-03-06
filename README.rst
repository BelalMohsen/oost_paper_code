Balanced Cross Sections, Shortening Estimates, and the Magnitude of Out-of-Sequence Thrusting in the Nankai Trough Accretionary Prism, Japan
===================

This is a repository of data and calculations for an upcoming paper.  A draft
of the paper is available at:
http://www.geology.wisc.edu/~jkington/Kington-OOST_Paper.pdf

This work extensively references and depends on the results of another
unpublished (so far) study, which is available here:
http://www.geology.wisc.edu/~jkington/Kington-OuterWedgeStructure.pdf

This work was also presented at the 2013 Fall AGU Meeting. The poster is available at:
http://www.geology.wisc.edu/~jkington/2013_AGU_Poster_color_coded_reduced.pdf

The 3D inclined shear method used to restore the horizons is implemented in the 
``fault_kinematics`` library: https://github.com/joferkington/fault_kinematics. 
The Python scripts in this repository handle the site and project specific
calculations and visualizations.


Abstract
--------

Out-of-sequence thrusting seaward of the Kumano Basin in the Nankai
Accretionary Prism, Japan has been a focus of extensive recent work and
multiple IODP expeditions. However, the amount of shortening and along strike
motion accommodated by the thrusts has not been studied in detail. We constrain
the total amount of shortening accommodated by the out-of-sequence thrust
system (OOSTS) in two ways. First, we compare the total shortening accommodated
by all other structures in the outer wedge to the amount of shortening
predicted by plate motions. Bed-length balancing of structures suggests that
the outer wedge has accommodated 75±16 km of shortening over the last 2.3±0.2
myr, while plate motion models [Loveless & Meade, 2010] predict 99±10 km of
convergence between the forearc block and the subducting Philippine Sea Plate.
If we assume that all other shortening is accommodated by the out-of-sequence
thrust system, this predicts 24±19 km of shortening on the OOSTS. For the
second method, we use fault geometry and syn-kinematic forearc stratigraphy to
model the magnitude and direction of slip on the zone’s youngest structure.
Modeling growth stratigraphy within the forearc basin using inclined shear
along the observed 3D fault geometry predicts 15±2 km of shortening (14±2 km
dip-slip, 6±1 km right-lateral strike-slip) accommodated by the younger of the
two major thrusts in the OOSTS. Additionally, the growth strata in the forearc
older than ∼0.5 Ma are best fit by oblique slip along the fault at an azimuth
of 321°, subparallel to plate motion. The growth strata also constrain uplift
of the forearc to have begun no earlier than 0.9-1.04 Ma and to have continued
until sometime more recently than ∼0.5 Ma. In contrast, Gulick, et al [2010]
concluded that uplift of the forearc began at 1.24-1.34 Ma and ended by
0.9-1.04 Ma. Our constraints on the timing suggests that there was a ∼0.2-0.3
myr period between activity on older and younger thrusts in the OOSTS when
shortening was primarily accommodated on structures near the toe of the
accretionary prism. Furthermore, comparing the duration of activity with our
estimates for the motion on each structure in the OOSTS suggests that each of
the two thrusts accommodated ∼~40% of the total plate convergence during the
time that they were active. 

Requires
--------

  * Python 2.6 or 2.7 
  * Matplotlib >= 1.0
  * Numpy >= 1.5
  * Scipy >= 0.6
  * h5py >= 2.0
  * Uncertainties >= 2.0

  * Python-geoprobe
  * <https://github.com/joferkington/fault_kinematics>
  * <https://github.com/joferkington/seismic_plotting>

  Some visualizations (e.g. ``interactive_inclined_shear.py``) require Mayavi and Tvtk.

Key Files
--------
`shortening_calculations.py <https://github.com/joferkington/oost_paper_code/blob/master/shortening_calculations.py>`_
        Calculation of shortening and error from line-length balancing and
        plate convergence.
`process_bootstrap_results.py <https://github.com/joferkington/oost_paper_code/blob/master/process_bootstrap_results.py>`_
        Calculates shortening (and errors) parallel to the section line from
        the saved results of bootstrapping the inclined-shear restoration.  
`bootstrap_error.py <https://github.com/joferkington/oost_paper_code/blob/master/basic.py>`_
	Runs a parallel monte-carlo inversion to estimate both the amount of
	slip and the error in the estimate. This inverts for slip 200 times for
	each horizon, using boostrapping with replacement on the points in both
	the horizon and fault geometries. The results are stored in
	``bootstrap.hdf5``.
`basic.py <https://github.com/joferkington/oost_paper_code/blob/master/basic.py>`_
	A simple best-fit inversion of the amount of slip along the fault to
        restore each horizon to horizontal.  For the paper, the results are
        obtained from ``bootstrap_error.py``, but this demonstrates a single,
        best-fit inversion.

Plotting
--------
`plot_bootstrap_results.py <https://github.com/joferkington/oost_paper_code/blob/master/plot_bootstrap_results.py>`_
        Plots slip over time with error ellipses. Generates the base for Figure
        8 in the paper.
`plot_dip_development.py <https://github.com/joferkington/oost_paper_code/blob/master/plot_dip_development.py>`_
        Plots present-day strike and dip of forearc stratigraphy. Generates the
        base for Figure 9 in the paper.
`plot_line_balancing_and_plate_motion.py <https://github.com/joferkington/oost_paper_code/blob/master/plot_line_balancing_and_plate_motion.py>`_
        Plots the results of the bootstrapped inclined shear restoration.
`forearc_detail_section.py <https://github.com/joferkington/oost_paper_code/blob/master/forearc_detail_section.py>`_
	Plots a detailed cross section through the uplifted forearc basin
	stratigraphy. The base plot for Figure 3 in the paper.
`error_ellipse.py <https://github.com/joferkington/oost_paper_code/blob/master/interactive_inclined_shear.py>`_
        Utilities for plotting error ellipses.

3D Plotting
-----------
`interactive_basic.py <https://github.com/joferkington/oost_paper_code/blob/master/interactive_basic.py>`_
        An interactive 3D visualization of the results. Displays the restored
        position of one of the horizons and the fault geometry and lets the
        user simulate slip on the fault.
`interactive_inclined_shear.py <https://github.com/joferkington/oost_paper_code/blob/master/interactive_inclined_shear.py>`_
        Functions used in ``interactive_basic.py``. Displays the present day
        geometries of the fault and a horizon and lets the user simulate slip
        on the fault.  
`visualize_solution.py <https://github.com/joferkington/oost_paper_code/blob/master/visualize_solution.py>`_
        An interactive 3D visualization of of the results.

Additional Calculations
-----------------------
`depth_conversion_simple.py <https://github.com/joferkington/oost_paper_code/blob/master/depth_conversion_simple.py>`_
	Builds a 1D time-depth *for the fault surface beneath the forearc* (and
	only the fault surface beneath the forearc) using the observed fault
	geometry in both time and depth.  (We didn't have access to the
	velocity model for the 3D volume at the time.) This is then applied to
	the fault surface picked from the 2D data to convert it to depth.
`fit_shear_angle.py <https://github.com/joferkington/oost_paper_code/blob/master/fit_shear_angle.py>`_
	Finds the best fitting shear angle for each horizon using a grid search.
`sequential_restoration.py <https://github.com/joferkington/oost_paper_code/blob/master/sequential_restoration.py>`_
        Attempt to invert for slip where the horizons are not restored
        independently.  This gives identical results as the independent version
        (``basic.py`` and ``bootstrap_error.py``). This demonstrates that the
        result is not sensitive to the fact that each horizon is restored
        independently of the one before it.

Other
-----
`data.py <https://github.com/joferkington/oost_paper_code/blob/master/data.py>`_
	Locations of datafiles and transform utilities.
`utilities.py <https://github.com/joferkington/oost_paper_code/blob/master/utilities.py>`_
        Various utility functions used throughout the project.
`restore_horizons.py <https://github.com/joferkington/oost_paper_code/blob/master/restore_horizons.py>`_
        Restores horizons (same as ``basic.py``) and writes the restored
        horizons out as geoprobe horizon files.
`sequential_restoration_cross_section.py <https://github.com/joferkington/oost_paper_code/blob/master/sequential_restoration_cross_section.py>`_
        Plots Figure 7 in the paper.
`grid_search.py <https://github.com/joferkington/oost_paper_code/blob/master/grid_search.py>`_
        Preforms a grid search for the best fit and displays the "roughness" of
        the horizon (i.e. misfit) at each point in the grid and displays the
        misfit surface.  This demonstrates that there are few local minima,
        validating the choice of basic "gradient descent" inversions.
