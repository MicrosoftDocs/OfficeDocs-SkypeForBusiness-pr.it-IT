---
title: Configurare il servizio Conformità per il server Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 'Riepilogo: informazioni su come configurare il servizio di conformità del server di chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 54131eeddc95afd71978ada3a84fba3d4ab52716
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817237"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configurare il servizio Conformità per il server Chat persistente

**Riepilogo:** Informazioni su come configurare il servizio di conformità del server di chat persistente in Skype for Business Server 2015.

La conformità della chat persistente consente agli amministratori di gestire un archivio di messaggi di chat persistenti e attività. Il servizio conformità registra e archivia i dati relativi a ogni conversazione del server di chat persistente, anche quando un partecipante:

- Si unisce a una chat room persistente

- Lascia una chat room

- Pubblica un messaggio

- Cronologia chat visualizzazioni

- Carica un file

- Download di un file

Queste informazioni possono essere recuperate dal database SQL di conformità in base alle esigenze. 

> [!NOTE]
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>Configurare il servizio di conformità tramite Windows PowerShell

Dopo che il servizio conformità è stato abilitato usando il generatore di topologie, è possibile configurare il servizio usando il cmdlet **set-CsPersistenChatComplianceConfiguration** :

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

o

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

Puoi impostare i parametri seguenti:

- AdapterType-consente di specificare il tipo di adapter. Un adattatore è un prodotto di terze parti che converte i dati nel database di conformità in un formato specifico. L'impostazione predefinita è XML.

- OneChatRoomPerOutputFile: questo parametro consente di specificare i report separati da creare per ogni chat room.

- AddChatRoomDetails-se abilitato, questo parametro registra altri dettagli su ogni chat room nel database. Poiché questa impostazione può aumentare notevolmente le dimensioni del database, è disabilitata per impostazione predefinita.

- AddUserDetails-se abilitato, questo parametro registra altri dettagli su ogni utente della chat room nel database. Poiché questa impostazione può aumentare notevolmente le dimensioni del database, è disabilitata per impostazione predefinita.

- Identity: questo parametro consente l'ambito delle impostazioni di conformità per una determinata raccolta, inclusi i livelli globale, del sito e dei servizi. L'impostazione predefinita è il livello globale. 

- RunInterval: questo parametro determina la quantità di tempo prima che il server crei il file di output di conformità successivo (il valore predefinito è 15 minuti).

## <a name="use-a-customized-compliance-adapter"></a>Usare un adattatore di conformità personalizzato

È possibile scrivere una scheda personalizzata invece di usare l'XmlAdapter installato con il server di chat persistente. A questo scopo, devi specificare un assembly .NET Framework che contiene una classe pubblica che implementa l'interfaccia **IComplianceAdapter** . È necessario inserire questo assembly nella cartella di installazione del server di chat persistente di ogni server nel pool del server di chat persistente. Uno dei server di conformità può specificare i dati di conformità alla scheda, ma i server di conformità non forniranno i dati di conformità duplicati a più istanze della scheda.

L'interfaccia è definita nell'assembly Compliance. dll nello spazio dei `Microsoft.Rtc.Internal.Chat.Server.Compliance`nomi. L'interfaccia definisce due metodi che devono essere implementati dall'adapter personalizzato.

Il server di conformità della chat persistente chiamerà il metodo seguente quando l'adapter viene caricato per primo. `AdapterConfig` Contiene la configurazione della conformità della chat persistente pertinente per la scheda conformità:

```cpp
void SetConfig(AdapterConfig config)
```

Il server di conformità della chat persistente chiama il metodo seguente a intervalli periodici, purché siano presenti nuovi dati da tradurre. Questo intervallo di tempo è uguale a `RunInterval` quello impostato nella configurazione della conformità della chat persistente:

```cpp
void Translate(ConversationCollection conversations)
```

`ConversationCollection` Contiene le informazioni sulla conversazione raccolte dall'ultima volta che è stato chiamato questo metodo.

## <a name="customize-the-xslt-definition-file"></a>Personalizzare il file di definizione XSLT

I dati di conformità vengono recapitati come XML, che è possibile trasformare nel formato più adatto all'organizzazione, usando un file di definizione XSLT. Questo argomento descrive il file XML creato dal servizio conformità. Vengono inoltre forniti esempi di file di definizione e di output XSLT.

### <a name="output-format"></a>Formato di output

L'output del servizio di conformità è categorizzato per conversazione (l'elemento di conversazione) e quindi per messaggio (elemento Messages), come illustrato nell'esempio di codice seguente:

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

Un elemento Conversation contiene quattro elementi (Channel, FirstMessage, StartTimeUTC e EndTimeUTC). L'elemento Channel contiene l'URI (Uniform Resource Identifier) della chat room e l'elemento FirstMessage descrive il primo messaggio nell'elemento Messages. Gli elementi StartTimeUTC e EndTimeUTC consentono gli orari di inizio e di fine della conversazione, come illustrato nell'esempio di codice seguente:

```XML
<<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

Un elemento Message contiene due elementi (sender e DateTimeUTC) e tre attributi (Type, Content e ID). L'elemento sender rappresenta l'utente che invia il messaggio e l'elemento DateTimeUTC rappresenta quando si verifica un evento, come illustrato nell'esempio di codice seguente:

```XML
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

La tabella seguente descrive il tipo di attributi del messaggio, il contenuto e l'ID.

**Attributi degli elementi messages**

|**Attributo**|**Descrizione**|**Facoltativo/obbligatorio**|
|:-----|:-----|:-----|
|Tipo  <br/> |Specifica il tipo di messaggio. I tipi di messaggio sono descritti nella tabella tipi di messaggi degli elementi del messaggio.  <br/> |Obbligatorio  <br/> |
|Contenuto  <br/> |Contiene il contenuto del messaggio. I messaggi con un tipo di join o parte non usano questo attributo.  <br/> |Facoltativo  <br/> |
|ID  <br/> |Specifica l'ID univoco del contenuto. Questo attributo viene usato solo con i messaggi con un tipo di chat.  <br/> |Facoltativo  <br/> |

Ogni elemento sender contiene cinque attributi: il nome utente, l'ID, la posta elettronica, l'interno e l'URI. Questi attributi sono descritti nella tabella seguente.

**Attributi degli elementi mittente**

|**Attributo**|**Descrizione**|**Facoltativo/obbligatorio**|
|:-----|:-----|:-----|
|Username  <br/> |Nome del mittente.  <br/> |Facoltativo  <br/> |
|ID  <br/> |ID univoco del mittente.  <br/> |Obbligatorio  <br/> |
|Posta elettronica  <br/> |Indirizzo di posta elettronica del mittente.  <br/> |Facoltativo  <br/> |
|Interno  <br/> |Determina se l'utente è un utente interno o un utente federato. Se il valore è impostato su true, l'utente è Internal.  <br/> |Facoltativo  <br/> |
|URI  <br/> |URI SIP dell'utente.  <br/> |Obbligatorio  <br/> |

Gli esempi seguenti mostrano i tipi di messaggio che l'elemento Messages può contenere. Vengono inoltre illustrati gli esempi di utilizzo di ogni elemento.

Join-un utente partecipa a una chat room.

```XML
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

Parte-un utente lascia una chat room.

```XML
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

Chat: l'indirizzo di posta elettronica del mittente.

```XML
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

Backchat-un utente richiede contenuto dalla cronologia chat.

```XML
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

Upload di file: un utente carica un file.

```XML
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

Download di file: un utente scarica un file.

```XML
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>XSD di output della chat persistente predefinito e la trasformazione XSL di esempio

L'esempio di codice seguente contiene l'output predefinito del server di conformità:

```XML
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

```XML
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
