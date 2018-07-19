### What’s MeasurementLab?

MeasurementLab (M-Lab) is a consortium of research, industry and public-interest partners dedicated to:
* Providing an open, verifiable measurement platform for global network performance
* Hosting the largest open Internet performance dataset on the planet
* Creating visualizations and tools to help people make sense of Internet performance

* Website: http://measurementlab.net/
* Github: https://github.com/m-lab
* Getting Started with BigQuery Documentation:   https://www.measurementlab.net/data/docs/bq/quickstart/


### Hackathon Projects

We have a few different projects for the hackathon related to data analysis or tool development.

**Project 1 (easy) -- ASN Annotation**: Extend our [Annotation Service](https://github.com/m-lab/annotation-service) to annotate test data with the correct ASN information from Maxmind. As data is run through our [ETL pipeline](https://github.com/m-lab/etl) or our [gardener processing service](https://github.com/m-lab/etl-gardener), it is annotated with relevant fields from Maxmind, e.g. location information. We would like to extend the annotation to include ASN data, and have that ASN data be correct at the time that the test was run, i.e. not the most recent Maxmind file, but the Maxmind historic data that matches the correct ASN assignment at the time of data collection. The data should all be available via Maxmind.

**Project 2 (medium/advanced) -- [SignalSearcher](https://github.com/m-lab/signal-searcher)**: SignalSearcher is our analysis toolkit for applying TensorFlow models to M-Lab data. Thus far we have an example that looks for significant/anomalous degredation or improvement that might signal an interconnection issue. We are interested in questions around detecting internet anomalies (e.g. large scale internet events, internet shutdowns, nation-state interference, country or ASN throttling). At the moment SignalSearcher only works on NDT data, so there's also an opportunity to bring in additional data sets, e.g. Paris Traceroute data, or external data sets, e.g. BGP or OONI measurements). Additionally, we haven't yet explored ways that we might want to surface events in our [visualization tools](https://github.com/m-lab/mlab-vis-client/), so exploring how to visually present anomalies would also be of interest.

**Project 3 (advanced) -- [Paris Traceroute](https://console.cloud.google.com/storage/browser/m-lab/paris-traceroute/) Data Analysis**: Everytime any test is run against the M-Lab platform, a Paris Traceroute test is trigged from the M-Lab server back to the client. As of yet, there's been minimal analysis of PTR data, so the sky is the limit. We've brainstormed ideas around combining path data with NDT measurements, as well as looking at paths that cross country boundaries, just to give some ideas here.

**Project 4 (medium) -- NDTjs Mock Testing Environment**: NDT can be integrated into applications to provide measurement as a service. More and more we are seeing interest in integration NDT into webbased applications, but as of yet we do not have a good local testing environment for the NDTjs library. Ideally this would include the ability to run a local mock NDT server, and have unit tests built in so that an implementer would be able to test their application.

Related Links:
* https://github.com/ndt-project/ndt-javascript-client
* https://github.com/opentechinstitute/mlab-speedtest
* https://github.com/m-lab/ndt/tree/master/HTML5-frontend

**Project 5 (medium) -- Extend the M-Lab Viz Platform**: Our visualization platform is built in React and D3 and can be easily extended to include new visualizations. You could develop new visualization techniques that allow users to understand and analyze the measurements in new ways, add datasets to the visualization tool, or explore ways to surface anomalies (either from [SignalSearcher](https://github.com/m-lab/signal-searcher) or [M-Lab Data Annotations](https://github.com/m-lab/data-annotations)).

**Project 6 (easy) -- Browser Extension**:  We have had a beta [Chrome extension](https://github.com/opentechinstitute/measure-app-legacy) for a few years now, but we'd love to have a Firefox Extension as well, and we'd welcome feature improvements to the current Chrome Extension.

### Contact us:

We will have a few team members at SIGCOMM, most likely Peter Boothe (pboothe@measurementlab.net) and Georgia Bullen (georgia@measurementlab.net). You can also contact the broader team by emailing support@measurementlab.net or pose questions to the community on our discuss list (discuss@measurementlab.net).
