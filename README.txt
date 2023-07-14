##########################################
##  Ajit Kumar Mehta - ajit_mehta@ucsb.edu  ##
##########################################

  ----    New binary black hole (BBH) mergers in the O3b data    ----

This repository contains parameter estimation (PE) posteriors for the
ten new BBH merger events found in the LIGO--Virgo collaboration (LVC)
data from the second half of the third observing run (O3b) using the
IAS pipeline (described in doi:10.1103/PhysRevD.100.023011 and
doi:10.1103/PhysRevD.101.083030). These results are presented in
(arxiv) (please cite this paper if using samples).

The directory Data contains a .npz for each event, which includes the
data and power spectral density (PSD) at each detector in the frequency
domain, and the grid of frequencies (in Hz) at which they are defined.

The parameters included in the feather files
<prior>/<evname>_posterior_samples.feather
are defined below.

*Note* all masses are in units of solar mass.

*Note* the variables iota and vphi correspond to the lalsimulation
parameters inclination and phiRef, respectively, which are defined
at the reference epoch (time when 22 frequency is f_ref).

param_names = {'mchirp': 'Detector Frame Chirp Mass',
               'q': 'Mass Ratio',
               'chieff': 'Effective Spin',
               'm1': 'Detector Frame Larger Mass',
               'm2': 'Detector Frame Smaller Mass',
               'mtot': 'Detector Frame Total Mass',
               'm1_source': 'Source Frame Larger Mass',
               'm2_source': 'Source Frame Smaller Mass',
               'mtot_source': 'Source Frame Total Mass',
               'mchirp_source': 'Source Frame Chirp Mass',
               'd_luminosity': 'Luminosity Distance (Mpc)',
               'd_comoving': 'Comoving Distance (Mpc)',
               'z': 'Redshift',
               's1x': '(Dimensionless) Spin X-Component of Larger Mass',
               's1y': '(Dimensionless) Spin Y-Component of Larger Mass',
               's1z': '(Dimensionless) Spin Z-Component of Larger Mass',
               's2x': '(Dimensionless) Spin X-Component of Smaller Mass',
               's2y': '(Dimensionless) Spin Y-Component of Smaller Mass',
               's2z': '(Dimensionless) Spin Z-Component of Smaller Mass',
               'ra': 'Right Ascension (rad)',
               'dec': 'Declination (rad)',
               'psi': 'Polarization Phase (rad)',
               'vphi': 'Orbital Phase (rad)',
               'iota': 'Inclination (rad)',
               'tgps_geocenter': 'GPS Time (s) at Geocenter',
               'tgps_H': 'GPS Time (s) at Hanford',
               'tgps_L': 'GPS Time (s) at Livingston',
               'tgps_V': 'GPS Time (s) at Virgo',
               'f_ref': 'Reference Frequency (Hz)',
               'f_lo': Minimum Frequency (Hz) in Analysis Band,
               'f_hi': Maximum Frequency (Hz) in Analysis Band,
               'lnl': 'Log Likelihood',
               'lnl_aux_H': 'Hanford Log Likelihood (Stationary Noise)',
               'lnl_aux_L': 'Livingston Log Likelihood (Stationary Noise)',
               'lnl_aux_V': 'Virgo Log Likelihood (Stationary Noise),
               'asd_drift_H': 'Hanford Amplitude Spectral Density Drift Correction',
               'asd_drift_L': 'Livingston Amplitude Spectral Density Drift Correction',
               'asd_drift_V': 'Virgo Amplitude Spectral Density Drift Correction'}
               

There is also an HDF file called IAS_O3b_triggers.hdf containing all of the
triggers with FAR below 1 per day. It has a single group ('triggers'),
and the dataset keys follow the conventions of the 4-OGC data release
(https://github.com/gwastro/4-ogc/blob/master/search/4-OGC_small.hdf),
except that our trigger times are in 'linear-free' coordinates
(note that these two conventions differ by a shift that depends on 
the intrinsic parameters, with a difference less than 0.1s for most sources
but up to roughly 0.3s for the lightest BBH systems).
