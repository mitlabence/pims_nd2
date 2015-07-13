pims_nd2
========

This package lets [pims](https://github.com/soft-matter/pims) interface with the [ND2SDK](http://www.nd2sdk.com) for fast reading of Nikon *.nd2 files.
Currently, this is only implemented for windows and Python 2.7.

SDKs for Linux and OSX are already included, these are probably easy to implement.

Dependencies
------------

Apart from [pims](https://github.com/soft-matter/pims) there are no extra dependencies. The required c libraries are included and will be added to the PATH variable at runtime. 

Examples
--------

The following code opens the demo file included in the package and iterates through the first 3 frames. Note that frames are only read when necessary.

    from pims_nd2 import ND2_Reader
    frames = ND2_Reader('cluster.nd2')
	frames.bundle_axes = 'zyx'
	for frame in frames[:3]:
		# do something

Metadata access can be done on two levels: reader level and frame level.

	frames.metadata['mpp']  # calibration in microns per pixel
	frames[0].metadata['t_ms']  # timestamp of image in milliseconds

Supporting Grant
----------------
This reader was developed by Casper van der Wel, as part of his PhD thesis work in Daniela Kraft’s group at the Huygens-Kamerlingh-Onnes laboratory, Institute of Physics, Leiden University, The Netherlands. This work was supported by the Netherlands Organisation for Scientific Research (NWO/OCW).