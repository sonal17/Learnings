* http://www.iis.net/configreference/system.webserver/staticcontent/clientcache
* madskristensen.net/post/performance-tuning-tricks-for-aspnet-and-iis-7-e28093-part-2
* http://madskristensen.net/post/performance-tuning-tricks-for-aspnet-and-iis-7-part-1
* http://stackoverflow.com/questions/7541032/caching-specific-javascript-and-css-files
* blog.janjonas.net/2011-08-21/microsoft-iis-7-enable-client-side-browser-caching-static-content-web-config

http://stackoverflow.com/questions/3929284/how-do-i-disable-caching-of-an-individual-file-in-iis-7-using-weserver-config-se
http://goobbe.com/questions/3464829/how-to-configure-static-content-cache-per-folder-and-extension-in-iis7

******************************** Static and dynamic compression in IIS 7/7.5 ************************8

* http://www.iis.net/configreference/system.webserver/urlcompression
<configuration>
   <system.webServer>
      <urlCompression doStaticCompression="true" doDynamicCompression="false" />
   </system.webServer>
</configuration>

* doDynamicCompression
Note: In IIS 7.0, the use of dynamic compression was disabled by default because of increased processor utilization 
that may have reduced the overall performance of the Web server. In IIS 7.5, changes were made to 
dynamic compression that resulted in better performance, so dynamic compression is enabled by default in IIS 7.5 and later.
The default value is true.

* doStaticCompression
Optional Boolean attribute.
Specifies whether static compression is enabled for URLs.
The default value is true.

* dynamicCompressionBeforeCache
Optional Boolean attribute.
Specifies whether the currently available response is dynamically compressed before it is put into the output cache.
The default value is false.

* http://www.codeproject.com/Articles/242133/Making-the-most-out-of-IIS-compression-Part-conf

* http://fullsocrates.wordpress.com/2012/07/31/enabling-http-compression-to-save-network-cost-in-iis7-x-23/
<httpCompression directory=”%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files”>
    <scheme name=”gzip” dll=”%Windir%\system32\inetsrv\gzip.dll” />
    <dynamicTypes>
        <add mimeType=”text/*” enabled=”true” />
        <add mimeType=”message/*” enabled=”true” />
        <add mimeType=”application/x-javascript” enabled=”true” />
        <add mimeType=”*/*” enabled=”false” />
    </dynamicTypes>
    <staticTypes>
        <add mimeType=”text/*” enabled=”true” />
        <add mimeType=”message/*” enabled=”true” />
        <add mimeType=”application/javascript” enabled=”true” />
        <add mimeType=”*/*” enabled=”false” />
    </staticTypes>
</httpCompression>


*** know how file caching shows up on the response header
http://sharepointinterface.com/2011/02/21/client-server-interactions-and-the-max-age-attribute-with-sharepoint-blob-caching/
