.. _doc_routinator_metrics_prometheus:

Prometheus Metrics
==================

Routinator's :ref:`monitoring service <doc_routinator_monitoring>` provides 
comprehensive metrics in Prometheus format at the :command:`/metrics` endpoint.
Here you can find an overview of all metrics and their meaning.

``routinator_{ta,repository}_valid_vrps_total``
    The total number of :term:`VRPs <Validated ROA Payload (VRP)>` found to be
    present and valid. This metric is exposed for each trust anchor and 
    repository.
    
``routinator_{ta,repository}_invalid_vrps_total``
    The total number of :term:`VRPs <Validated ROA Payload (VRP)>` found to be
    invalid. This metric is exposed for each trust anchor and repository.
        
