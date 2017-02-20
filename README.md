# fio-parser

Analyze fio output and send metrics to Graphite.

An example as follows:

    $ python fio-parser.py -d /opt/fio/profiles/results -s <graphite_host>

Note:

- This script has a python lib dependency, make sure running `pip install graphitesend` beforehand.
- The output directory should be an absolute path.
- The metrics can be defined using `-m`, metric name is a '.' separated string each part of which comes from fio job output. However, there is an exception for percentile, please replace '.' with ',' for the number. For example, `-m read.bw write.clat.percentile.99,500000`
- After handling output file, a suffix('.bak') will be added to the file name to avoid duplicate handling.