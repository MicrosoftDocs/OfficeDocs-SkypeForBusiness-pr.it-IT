---
title: Modificare le impostazioni di configurazione del trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi. '
ms.openlocfilehash: 76196df2cf0bd74ef804a082862891c326048408
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816956"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Modificare le impostazioni di configurazione del trunk SIP in Skype for Business Server

Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi. Queste impostazioni eseguono operazioni come specifica:

- Se il bypass multimediale deve essere abilitato nei trunk.
- Condizioni in cui vengono inviati i pacchetti RTCP (Real-Time Transport Control Protocol).
- Indipendentemente dal fatto che sia necessaria o meno la crittografia SRTP (Real-Time Protocol) in ogni trunk.

Quando si installa Skype for Business Server, viene creata una raccolta globale di impostazioni di configurazione trunk SIP. Gli amministratori possono inoltre creare raccolte di impostazioni personalizzate nell'ambito del sito o nell'ambito del servizio (solo per il servizio gateway PSTN). Una qualsiasi di queste raccolte può essere modificata in seguito usando il pannello di controllo di Skype for Business Server o Windows PowerShell.

Quando si modificano le impostazioni di configurazione del trunk SIP tramite il pannello di controllo di Skype for Business Server Server, sono disponibili le opzioni seguenti:

|Impostazione dell'interfaccia utente |Parametro di PowerShell |Descrizione |
|--|--|--|
|Nome|Identity|Identificatore univoco per la raccolta. Questa proprietà è di sola lettura; non è possibile modificare l'identità di una raccolta di impostazioni di configurazione trunk.|
|Descrizione|Descrizione|Consente agli amministratori di archiviare informazioni di aggiunta sulle impostazioni, ad esempio lo scopo della configurazione trunk.|
|Finestre di dialogo iniziali massime supportate|MaxEarlyDialogs|Numero massimo di risposte a forcella un gateway PSTN, IP-PBX o SBC presso il provider di servizi può ricevere un invito inviato al Mediation Server.|
|Livello di supporto della crittografia|SRTPMode|Indica il livello di supporto per la protezione del traffico multimediale tra il Mediation Server e il gateway PSTN, IP-PBX o SBC presso il provider di servizi. Nel caso del bypass multimediale, questo valore deve essere compatibile con l'impostazione di EncryptionLevel nella configurazione degli elementi multimediali. La configurazione multimediale viene impostata usando i cmdlet New-CsMediaConfiguration e Set-CsMediaConfiguration.<br/>I valori consentiti sono:<br/><br/>**Obbligatorio**: è necessario usare la crittografia SRTP.<br/>**Facoltativo**: SRTP verrà usato se il gateway lo supporta.<br/>**Non supportata**: la crittografia SRTP non è supportata e pertanto non verrà usata.<br/><br/>SRTPMode viene usato solo se il gateway è configurato per l'uso di Transport Layer Security (TLS). Se il gateway è configurato con il protocollo TCP (Transmission Control Protocol) come trasporto, SRTPMode è impostato internamente su non supportato.|
|Fare riferimento al supporto|Enable3pccRefer<br/>EnableReferSupport|Se impostato per **abilitare l'invio, fare riferimento al gateway**, indica che il trunk supporta la ricezione di richieste di riferimento dal server Mediation.<br/>Se impostato per **abilitare l'opzione fai riferimento tramite il controllo delle chiamate di terze parti**, indica che il protocollo 3PCC può essere usato per consentire alle chiamate trasferite di ignorare il sito ospitato. 3PCC è anche noto come "controllo di terze parti" e si verifica quando viene usata una terza parte per connettere una coppia di chiamanti (ad esempio, un operatore che effettua una chiamata dalla persona a alla persona B).|
|Abilitare il bypass multimediale|EnableBypass|Indica se il bypass multimediale è abilitato per il trunk. Il bypass multimediale può essere abilitato solo se è abilitata anche l' **elaborazione media centralizzata** .|
|Elaborazione multimediale centralizzata|ConcentratedTopology|Indica se è presente un punto di interruzione multimediale noto. Un esempio di punto di terminazione multimediale noto può essere costituito da un gateway PSTN in cui la terminazione degli elementi multimediali ha lo stesso IP della terminazione dei segnali.|
|Abilitare l'aggancio RTP|EnableRTPLatching|Indica se i trunk SIP supportano o meno il latching RTP. Il latching RTP è una tecnologia che consente la connettività RTP/RTCP tramite un dispositivo NAT (Network Address Translator) o un firewall.|
|Abilitare la cronologia delle chiamate inoltrate|ForwardCallHistory|Indica se le informazioni del registro chiamate verranno inoltrate tramite il trunk.|
|Abilitare inoltra P-asserzione-dati identità|ForwardPAI|Indica se l'intestazione PAI (P-Asserted-Identity) verrà inoltrata insieme alla chiamata. L'intestazione PAI consente di verificare l'identità del chiamante.|
|Abilitare il timer di failover del routing in uscita|EnableFastFailoverTimer|Indica se le chiamate in uscita non risposte dal gateway entro 10 secondi verranno instradate al successivo trunk disponibile. Se non ci sono trunk aggiuntivi, la chiamata verrà eliminata automaticamente. In un'organizzazione con reti lente e risposte del gateway, che potrebbero potenzialmente causare la perdita di chiamate inutilmente.|
|Usi PSTN associati|PSTNUsages|Raccolta di utilizzi PSTN assegnati al trunk.|
|Numero tradotto da testare|N/D|Numero di telefono che può essere usato per eseguire un test ad hoc delle impostazioni di configurazione del trunk.|
|Regole di traduzione associate|OutboundTranslationRulesList|Raccolta di regole di traduzione per i numeri di telefono che si applicano alle chiamate gestite dal routing in uscita (chiamate indirizzate a destinazioni PBX o PSTN).|
|Regole di traduzione del numero chiamate|OutboundCallingNumberTranslationRulesList|Raccolta di regole di conversione dei numeri in uscita assegnate al trunk.|
|Numero di telefono da testare|N/D|Numero di telefono che può essere usato per eseguire un test ad hoc sulle regole di traduzione.|
|Numero chiamante|N/D|Indica che il numero di telefono da testare è il numero di telefono del chiamante.|
|Numero chiamato|N/D|Indica che il numero di telefono da testare è il numero di telefono della persona che viene chiamata.|
|||

> [!Note]
> I cmdlet di Skype for Business Server CsTrunkConfiguration supportano altre proprietà non visualizzate nel pannello di controllo di Skype for Business Server. Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTrunkConfiguration) . 

**Per modificare le impostazioni di configurazione del trunk SIP tramite il pannello di controllo di Skype for Business Server**

1. Nel pannello di controllo di Skype for Business Server fare clic su **routing vocale**e quindi su **configurazione trunk**.
2. Nella scheda **configurazione trunk** fare doppio clic sulle impostazioni di configurazione trunk da modificare. Tieni presente che puoi modificare solo una raccolta di impostazioni alla volta. Se si desidera apportare le stesse modifiche in più insiemi, utilizzare invece Windows PowerShell.
3. Nella finestra di dialogo **modifica configurazione trunk** eseguire le selezioni appropriate e quindi fare clic su **OK**.
4. La proprietà state per la raccolta verrà aggiornata in UNCOMMITTED. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **commit**e quindi su **commit tutti**.
5. Nella finestra di dialogo **impostazione configurazione vocale non impegnata**fare clic su **OK**.
6. Nella finestra di dialogo **Pannello di controllo di Skype for Business Server** fare clic su **OK**.
