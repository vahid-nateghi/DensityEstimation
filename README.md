# DensityEstimation
Matlab code for global thermospheric density estimation using two-line element data.


Copyright © 2019 by David Gondelach

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.


Disclaimer: 
This code is under development and may not directly run after installation. The code and instructions are being updated.


Acknowlegdments:
The MATLAB code for Jacchia-Bowman 2008 model was developed by Meysam Mahooti (copyright 2018) and was downloaded from https://www.mathworks.com/matlabcentral/fileexchange/56163-jacchia-bowman-atmospheric-density-model (version 2.0.0.0).
The MATLAB code for the SGP4 model and several time and reference frame routines was developed by David Vallado (and others) and was downloaded from https://celestrak.com/software/vallado-sw.php.


References:
The density modeling and estimation techniques are described in:
@misc{gondelach2019realtime,
    title={Real-Time Thermospheric Density Estimation Via Two-Line-Element Data Assimilation},
    author={David Gondelach and Richard Linares},
    year={2019},
    eprint={1910.00695},
    archivePrefix={arXiv}
}
see https://arxiv.org/abs/1910.00695


Installation instructions:
1. Download the DensityEstimation Matlab code
2. Download and install SPICE Toolkit for Matlab: https://naif.jpl.nasa.gov/naif/toolkit_MATLAB.html
3. Set the path to the SPICE Toolkit directory in mainDensityEstimation.m
4. Download SPICE kernels (i.e. ephemeris files) from https://naif.jpl.nasa.gov/pub/naif/generic_kernels/ and put them in the folder Data. Download the following kernel files: latest_leapseconds.tls, de430.bsp, pck00010.tpc, earth_fixed.tf, earthstns_itrf93_050714.bsp, earth_070425_370426_predict.bpc, earth_720101_070426.bpc, earth_latest_high_prec.bpc (see links below).
5. Download space weather file from Celestrak and put in folder Data: https://www.celestrak.com/SpaceData/SW-All.txt
6. Download Earth orientation data file from Celestrak and put in folder Data: https://www.celestrak.com/SpaceData/EOP-All.txt
7. Download 2 space weather files needed for the JB2008 model and put in folder Data: http://sol.spacenvironment.net/jb2008/indices/SOLFSMY.TXT  and  http://sol.spacenvironment.net/jb2008/indices/DTCFILE.TXT 
8. If you want to use automatic download of TLE data, then specify your “www.space-track.org” username and password in runDensityEstimationTLE.m. (Alternatively, you can download the TLE data manually and put them in the folder TLEdata with naming convention: [NORADID].tle, e.g. 12388.tle )
9. For each object used for estimation, specify the ballistic coefficient (BC) in the text file: Data/BCdata.txt


Run instructions:
1. Open mainDensityEstimation.m
2. Specify the time window for density estimation by setting the start year, month and day and number of days
3. (Optionally) select the reduced-order density model and the reduction order (default order: r=10)
4. (Optionally) select the objects to use for density estimation
5. Run mainDensityEstimation


Ephemeris file links:
latest_leapseconds.tls:  https://naif.jpl.nasa.gov/pub/naif/generic_kernels/lsk/
de430.bsp:  https://naif.jpl.nasa.gov/pub/naif/generic_kernels/spk/planets/
earthstns_itrf93_050714.bsp:  https://naif.jpl.nasa.gov/pub/naif/generic_kernels/spk/stations/
pck00010.tpc, earth_fixed.tf, earth_070425_370426_predict.bpc, earth_720101_070426.bpc, earth_latest_high_prec.bpc:  https://naif.jpl.nasa.gov/pub/naif/generic_kernels/pck/



David Gondelach, Sep 2019
email: davidgondelach@gmail.com
