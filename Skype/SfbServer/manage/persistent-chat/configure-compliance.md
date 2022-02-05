---
title: Configurare il servizio di conformità per il server Chat persistente in Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 'Riepilogo: informazioni su come configurare il servizio Conformità server Chat persistente in Skype for Business Server 2015.'
---

# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configurare il servizio di conformità per il server Chat persistente in Skype for Business Server 2015

**Riepilogo:** Informazioni su come configurare il servizio Conformità server Chat persistente in Skype for Business Server 2015.

La conformità di Persistent Chat consente agli amministratori di gestire un archivio dei messaggi di Persistent Chat e delle attività. Il servizio di conformità registra e archivia i dati relativi a ogni conversazione del server Chat persistente, incluso quando un partecipante:

- Partecipa a una chat room persistente

- Lascia una chat room

- Invia un messaggio

- Visualizza la cronologia della chat

- Carica un file

- Scarica un file

Queste informazioni possono essere recuperate dal database SQL conformità in base alle esigenze. 

> [!NOTE]
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento](/microsoftteams/upgrade-start-here). Se è necessario utilizzare persistent chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015. 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>Configurare il servizio di conformità tramite Windows PowerShell

Dopo aver abilitato il servizio di conformità utilizzando Generatore di topologie, è possibile configurare il servizio utilizzando il cmdlet **Set-CsPersistenChatComplianceConfiguration** :

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

oppure

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

È possibile impostare i parametri seguenti:

- AdapterType - Consente di specificare il tipo di scheda. Un adattatore è un prodotto di terze parti che converte i dati nel database di conformità in un formato specifico. XML è l'impostazione predefinita.

- OneChatRoomPerOutputFile - Questo parametro consente di specificare che devono essere creati report separati per ogni chat room.

- AddChatRoomDetails - Se abilitato, questo parametro registra ulteriori dettagli su ogni chat room nel database. Poiché questa impostazione può aumentare notevolmente le dimensioni del database, è disabilitata per impostazione predefinita.

- AddUserDetails: se abilitato, questo parametro registra ulteriori dettagli su ogni utente di chat room nel database. Poiché questa impostazione può aumentare notevolmente le dimensioni del database, è disabilitata per impostazione predefinita.

- Identity: questo parametro consente di includere le impostazioni di conformità nell'ambito di una raccolta specifica, inclusi i livelli globali, di sito e di servizio. Il valore predefinito è il livello globale. 

- RunInterval - Questo parametro determina l'intervallo di tempo prima che il server crei il file di output di conformità successivo (il valore predefinito è 15 minuti).

## <a name="use-a-customized-compliance-adapter"></a>Usare una scheda di conformità personalizzata

È possibile scrivere un adattatore personalizzato anziché utilizzare l'oggetto XmlAdapter installato con il server Chat persistente. A tale scopo, è necessario fornire un assembly .NET Framework contenente una classe pubblica che implementa **l'interfaccia IComplianceAdapter**. È necessario inserire questo assembly nella cartella di installazione del server Chat persistente di ogni server del pool di server Chat persistente. Uno qualsiasi dei server di conformità può fornire dati di conformità alla scheda, ma i server di conformità non forniranno dati di conformità duplicati a più istanze della scheda.

L'interfaccia è definita nell'assembly Compliance.dll nello spazio dei nomi  `Microsoft.Rtc.Internal.Chat.Server.Compliance`. L'interfaccia definisce due metodi che devono essere implementati dall'adattatore personalizzato.

Il server Conformità chat persistente chiamerà il metodo seguente al primo caricamento della scheda. Contiene  `AdapterConfig` la configurazione di conformità di Persistent Chat rilevante per la scheda di conformità:

```cpp
void SetConfig(AdapterConfig config)
```

Il server Di conformità di Persistent Chat chiama il metodo seguente a intervalli periodici, purché siano disponibili nuovi dati da tradurre. Questo intervallo di tempo è uguale a quello  `RunInterval` impostato nella configurazione di conformità di Persistent Chat:

```cpp
void Translate(ConversationCollection conversations)
```

Contiene  `ConversationCollection` le informazioni sulla conversazione raccolte dall'ultima chiamata a questo metodo.

## <a name="customize-the-xslt-definition-file"></a>Personalizzare il file di definizione XSLT

I dati di conformità vengono recapitati in formato XML, che è possibile trasformare nel formato più adatto all'organizzazione, utilizzando un file di definizione XSLT. Questo argomento descrive il file XML creato dal servizio di conformità. Sono inoltre disponibili esempi dei file di definizione XSLT e dei file di output.

### <a name="output-format"></a>Formato di output

L'output del servizio di conformità è classificato per conversazione (elemento Conversation) e quindi per messaggio (elemento Messages), come illustrato nell'esempio di codice seguente:

```XML
<?xml version="1.0" encoding="utf-8" ?> 
<Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Conversation>
    <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
    <!--FirstMessage goes here --!>
    <Messages> 
      <!—Messages go here--!>
    </Messages>
    <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
  </Conversation>
</Conversations>
```

Un elemento Conversation contiene quattro elementi (Channel, FirstMessage, StartTimeUTC e EndTimeUTC). L'elemento Channel contiene l'URI (Uniform Resource Identifier) della chat room e l'elemento FirstMessage descrive il primo messaggio nell'elemento Messages. Gli elementi StartTimeUTC e EndTimeUTC forniscono l'ora di inizio e di fine per la conversazione, come illustrato nell'esempio di codice seguente:

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

Un elemento Messages contiene due elementi (Sender e DateTimeUTC) e tre attributi (Type, Content e ID). L'elemento Sender rappresenta l'utente che invia il messaggio e l'elemento DateTimeUTC rappresenta quando si verifica un evento, come illustrato nell'esempio di codice seguente:

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

Nella tabella seguente vengono descritti gli attributi del messaggio Type, Content e ID.

**Attributi dell'elemento Messages**

|**Attributo**|**Descrizione**|**Facoltativo/Obbligatorio**|
|:-----|:-----|:-----|
|Tipo  <br/> |Specifica il tipo di messaggio. I tipi di messaggio sono descritti nella tabella Tipi di messaggio dell'elemento Messages.  <br/> |Obbligatorio  <br/> |
|Contenuto  <br/> |Contenuto del messaggio. Questo attributo non è utilizzato per i messaggi con Type Join o Part.  <br/> |Facoltativo  <br/> |
|ID  <br/> |Specifica l'ID univoco del contenuto. Questo attributo è utilizzato solo con i messaggi con Type Chat.  <br/> |Facoltativo  <br/> |

Ogni elemento Sender contiene cinque attributi, ovvero Username, ID, Email, Internal e Uri. Questi attributi sono descritti nella tabella seguente.

**Attributi dell'elemento Sender**

|**Attributo**|**Descrizione**|**Facoltativo/Obbligatorio**|
|:-----|:-----|:-----|
|Username  <br/> |Nome del mittente.  <br/> |Facoltativo  <br/> |
|ID  <br/> |ID univoco del mittente.  <br/> |Obbligatorio  <br/> |
|Posta elettronica  <br/> |Indirizzo di posta elettronica del mittente.  <br/> |Facoltativo  <br/> |
|Interno  <br/> |Determina se l'utente è interno o federato. Se il valore è impostato su true, l'utente è interno.  <br/> |Facoltativo  <br/> |
|URI  <br/> |URI SIP dell'utente.  <br/> |Obbligatorio  <br/> |

Negli esempi seguenti vengono mostrati i tipi di messaggio che l'elemento Messages può contenere. Sono inoltre disponibili esempi di utilizzo per ogni elemento.

Partecipa: un utente partecipa a una chat room.

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

Parte: un utente lascia una chat room.

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

Chat : indirizzo di posta elettronica del mittente.

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

Backchat - Un utente richiede il contenuto dalla cronologia delle chat.

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

Caricamento file: un utente carica un file.

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

Download file- Un utente scarica un file.

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>XSD di output di Persistent Chat predefinito e trasformazione XSL di esempio

L'esempio di codice seguente contiene l'output predefinito di Compliance Server:

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="Conversations" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
   <xs:simpleType name="ComplianceMessageType">
      <xs:restriction base="xs:string">
        <xs:enumeration value="JOIN"/>
        <xs:enumeration value="PART"/>
        <xs:enumeration value="CHAT"/>
        <xs:enumeration value="BACKCHAT"/>
        <xs:enumeration value="FILEUPLOAD"/>
        <xs:enumeration value="FILEDOWNLOAD"/>
      </xs:restriction>
    </xs:simpleType>

  <xs:element name="Sender">
    <xs:complexType>
      <xs:attribute name="UserName" type="xs:string" />
      <xs:attribute name="id" type="xs:int" />
      <xs:attribute name="email" type="xs:string" use="optional" />
      <xs:attribute name="internal" type="xs:boolean" use="optional" >
        <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
      </xs:attribute>
      <xs:attribute name="uri" type="xs:anyURI" use="optional" />
    </xs:complexType>
  </xs:element>
  <xs:element name="DateTimeUTC">
    <xs:complexType>
      <xs:attribute name="since1970" type="xs:long" />
      <xs:attribute name="string" type="xs:string" />
      <xs:attribute name="long" type="xs:long" />
    </xs:complexType>
  </xs:element>
  <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
    <xs:complexType>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element ref="Sender" />
        <xs:element ref="DateTimeUTC" />
        <xs:element name="Conversation">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="uri" type="xs:anyURI" />
                  <xs:attribute name="name" type="xs:string" use="optional" />
                </xs:complexType>
              </xs:element>
              <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                    <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                  </xs:sequence>
                  <xs:attribute name="type" type="ComplianceMessageType" />
                  <xs:attribute name="content" type="xs:string" />
                  <xs:attribute name="id" type="xs:int" />
                </xs:complexType>
              </xs:element>
              <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                      <xs:complexType>
                        <xs:sequence>
                          <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                          <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                        </xs:sequence>
                        <xs:attribute name="type" type="ComplianceMessageType" />
                        <xs:attribute name="content" type="xs:string" />
                        <xs:attribute name="id" type="xs:int" />
                      </xs:complexType>
                    </xs:element>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
              <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
              <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:choice>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

L'esempio di codice seguente contiene una trasformazione XSL di esempio:

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
   <xsl:output method="xml" encoding="UTF-8" indent="yes" />

   <xsl:template match="/">
      <FileDump>
         <xsl:apply-templates />
      </FileDump>
   </xsl:template>

   <xsl:template match="Conversation">
      <xsl:variable name="chanName" select="Channel/@name" />
      <Conversation Perspective="{$chanName}_group_channel">
         <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
         <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
         <xsl:apply-templates />
         <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
      </Conversation>
   </xsl:template>

   <xsl:template match="Message">
      <xsl:choose>
         <xsl:when test="@type='JOIN'">
            <ParticipantEntered>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantEntered>
         </xsl:when>

         <xsl:when test="@type='PART'">
            <ParticipantLeft>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantLeft>
         </xsl:when>

         <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
            <FileTransferStarted>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
            </FileTransferStarted>
            <FileTransferEnded>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
               <Status>Completed</Status>
            </FileTransferEnded>
         </xsl:when>

         <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
            <Message>
               <xsl:call-template name="DateTimeAndLogin" />
               <Content><xsl:value-of select="@content" /></Content>
            </Message>
         </xsl:when>

         <xsl:otherwise />
      </xsl:choose>
   </xsl:template>

   <xsl:template name="DateTimeAndLogin">
      <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
      <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
   </xsl:template>
</xsl:stylesheet>
```
