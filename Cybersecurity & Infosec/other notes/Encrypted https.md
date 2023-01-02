HTTPS connections negotiated via TLS 1.3 and ESNI (Encrypted Server Name Indication) prevent third-party observers from detecting what website a user is attempting to access. This effectively blinds surveillance tools from seeing what users are doing online.

There is a myth surrounding HTTPS connections that network observers (such as internet service providers) cannot see what users are doing. This is technically incorrect.

While HTTPS connections are encypted and prevent network observers from viewing/reading the contents of an HTTPS connection, there is a short period before HTTPS connections are established when third-parties can detect to what server the user is connecting.

This is done by looking at the HTTPS connection's SNI (Server Name Indication) field.

In HTTPS connections negotiated via older versions of the TLS protocol (such as TLS 1.1 and TLS 1.2), the SNI field is visible in plaintext.

In TLS 1.3, a protocol version launched in 2018, the SNI field can be hidden and encypted via ESNI.

As the TLS 1.3 protocol is seeing broader adoption today, ESNI usage is increasing as well, and more HTTPS connections are now harder to track for online censorship tools like the GFW.