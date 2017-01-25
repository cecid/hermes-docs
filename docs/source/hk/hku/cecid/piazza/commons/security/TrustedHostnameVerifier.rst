.. java:import:: java.util Collection

.. java:import:: java.util Iterator

.. java:import:: javax.net.ssl HostnameVerifier

.. java:import:: javax.net.ssl SSLSession

TrustedHostnameVerifier
=======================

.. java:package:: hk.hku.cecid.piazza.commons.security
   :noindex:

.. java:type:: public class TrustedHostnameVerifier implements HostnameVerifier

   TrustedHostnameVerifier is a HostnameVerifier which verifies the host name in an SSL session based on a list of pre-defined hostnames. If there is no such a list in this verifier, it defaults to trust any host name.

   :author: Hugo Y. K. Lam

Constructors
------------
TrustedHostnameVerifier
^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public TrustedHostnameVerifier()
   :outertype: TrustedHostnameVerifier

   Creates a new intance of TrustedHostnameVerifier. The verifier will be set to trust all hostnames on verification.

TrustedHostnameVerifier
^^^^^^^^^^^^^^^^^^^^^^^

.. java:constructor:: public TrustedHostnameVerifier(Collection hostnames)
   :outertype: TrustedHostnameVerifier

   Creates a new intance of TrustedHostnameVerifier.

   :param hostnames: the host names to be trusted on verification.

Methods
-------
verify
^^^^^^

.. java:method:: public boolean verify(String hostname, SSLSession sslSession)
   :outertype: TrustedHostnameVerifier

   Verifies that the host name is an acceptable match with the trusted host names pre-defined in this verifier.

   :param hostname: the host name.
   :param sslSession: the SSL session used on the connection to the host.
   :return: true if the host name is acceptable.

   **See also:** :java:ref:`javax.net.ssl.HostnameVerifier.verify(java.lang.String,
   javax.net.ssl.SSLSession)`

