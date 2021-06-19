.. _doc_routinator_metrics:

Metrics
=======

Routinator's :ref:`monitoring service <doc_routinator_monitoring>` provides 
comprehensive metrics in two formats:

 - JSON format at the :command:`/api/v1/status` endpoint
 - Prometheus format at the :command:`/metrics` endpoint
 
Here you can find an overview of all metrics and their meaning.

.. _doc_routinator_metrics_json:

JSON
""""

``version``
    The version of Routinator.
    
``serial``
    The current :term:`RTR <RPKI-to-Router (RPKI-RTR)>` serial number.
    
``now``
    The current date and time in UTC.
    
``lastUpdateStart``
    The date and time time in UTC that the last validation run started.
    
``lastUpdateDone``
    The date and time time in UTC that the last validation run completed.
    
``lastUpdateDuration``
    The duration of the last validation run, in seconds.
    
``tals``
    Metrics for each configured trust anchor. In most cases these will be the
    five Regional Internet Registries, but will include the trust anchors of
    any configured :ref:`testbeds <doc_routinator_testbed>` as well.
    
``vrpsTotal``
    The total number of :term:`VRPs <Validated ROA Payload (VRP)>` found to be
    present and valid.

``vrpsUnsafe``
    The number of :term:`VRPs <Validated ROA Payload (VRP)>` that are considered
    :term:`unsafe <Unsafe VRPs>`.

``vrpsLocallyFiltered``
    The number of :term:`VRPs <Validated ROA Payload (VRP)>` that are filtered
    as the result of a  :ref:`local exception
    <doc_routinator_local_exceptions>`.

``vrpsDuplicate``
    The number of duplicate :term:`VRPs <Validated ROA Payload (VRP)>` resulting
    from ROAs containing the same  authorisation.

``vrpsFinal``
    The number of :term:`VRPs <Validated ROA Payload (VRP)>` that is considered
    the final set provided to your  routers. It is the total number of VRPs,
    minus the ones that are unsafe, locally filtered and duplicate.

``validPublicationPoints``
    The number of valid :term:`publication points <Publication Point>`.

``rejectedPublicationPoints``
    The number of rejected :term:`publication points <Publication Point>`.

``validManifests``
    The number of valid :term:`manifests <Manifest>`.

``invalidManifests``
    The number of invalid :term:`manifests <Manifest>`.

``staleManifests``
    The number of :term:`stale <Stale Object>` :term:`manifests <Manifest>`.

``missingManifests``
    The number of missing :term:`manifests <Manifest>`.

``validCRLs``
    The number of valid :term:`certificate revocation lists <Certificate 
    Revocation List (CRL)>`.

``invalidCRLs``
    The number of invalid :term:`certificate revocation lists <Certificate 
    Revocation List (CRL)>`.

``staleCRLs``
    The number of :term:`stale <Stale Object>` :term:`certificate revocation
    lists <Certificate  Revocation List (CRL)>`.

``strayCRLs``
    The number of stray :term:`certificate revocation lists <Certificate 
    Revocation List (CRL)>`. This refers to a CRL listed on the manifest that is
    not also the CRL listed in the manifest’s EE certificate.

``validCACerts``
    The number of Certificate Authority certificates found to be present and
    valid.

``validEECerts``
    The number of End Entity certificates found to be present and valid

``invalidCerts``
    The number of invalid certificates.

``validROAs``
    The number of valid :term:`Route Origin Attestations <Route Origin 
    Attestation (ROA)>`

``invalidROAs``
    The number of invalid :term:`Route Origin Attestations <Route Origin 
    Attestation (ROA)>`.

``validGBRs``
    The number of valid :term:`Ghostbusters Records <Ghostbusters Record
    (GBR)>`.

``InvalidGBRs``
    The number of invalid :term:`Ghostbusters Records 
    <Ghostbusters Record (GBR)>`.

``otherObjects``
    The number of objects found that are not certificates (.cer), certificate 
    revocation lists (.crl), manifests (.mft), ROAs (.roa), or Ghostbuster 
    Records (.gbr).

.. _doc_routinator_metrics_prometheus:

Prometheus
""""""""""

``routinator_{ta,repository}_valid_vrps_total``
    The total number of :term:`VRPs <Validated ROA Payload (VRP)>` found to be
    present and valid. This metric is exposed for each trust anchor and 
    repository.
    
``routinator_{ta,repository}_invalid_vrps_total``
    The total number of :term:`VRPs <Validated ROA Payload (VRP)>` found to be
    invalid. This metric is exposed for each trust anchor and repository.
        
