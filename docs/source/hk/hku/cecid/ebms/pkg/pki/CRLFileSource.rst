.. java:import:: java.io File

.. java:import:: java.io FileInputStream

.. java:import:: java.io IOException

.. java:import:: java.io InputStream

.. java:import:: java.security.cert CRLException

.. java:import:: java.security.cert CertificateException

.. java:import:: java.security.cert CertificateFactory

.. java:import:: java.security.cert X509CRL

CRLFileSource
=============

.. java:package:: hk.hku.cecid.ebms.pkg.pki
   :noindex:

.. java:type:: public class CRLFileSource extends CRLSource

   This class extends CRLSource to add initialization procedure for loading a file-based CRL.

   :author: kcyee

Fields
------
crlFile
^^^^^^^

.. java:field:: protected File crlFile
   :outertype: CRLFileSource

   The file holding the CRL

Constructors
------------
CRLFileSource
^^^^^^^^^^^^^

.. java:constructor:: public CRLFileSource()
   :outertype: CRLFileSource

   Default constructor. It initializes the object. But the object is still unusable until init() is called.

CRLFileSource
^^^^^^^^^^^^^

.. java:constructor:: public CRLFileSource(String crlFile)
   :outertype: CRLFileSource

   Constructor with the file name of the CRL passed in. It initializes the object. But the object is still unusable until init() is called.

   :param crlFile: the file name of the CRL

CRLFileSource
^^^^^^^^^^^^^

.. java:constructor:: public CRLFileSource(File crlFile)
   :outertype: CRLFileSource

   Constructor with the file object holding the CRL passed in. It initializes the object. But the object is still unusable until init() is called.

   :param crlFile: the file object of the file holding the CRL

Methods
-------
init
^^^^

.. java:method:: public void init() throws CRLException
   :outertype: CRLFileSource

   Initializes the object. The CRL file is being loaded into the internal CRL object.

   :throws CRLException: Initialization error occurs

