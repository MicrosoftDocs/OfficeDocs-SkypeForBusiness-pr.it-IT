---
title: Skype for Business ServerModify SIP trunk configuration settings
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Le impostazioni di configurazione dei trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway di rete telefonica a commutazione pubblica, un PBX (Ip-Public Branch Exchange) o un Session Border Controller (SBC) presso il provider di servizi. '
ms.openlocfilehash: 0f856c83d6f521308343b626addc0ab2c5e16792
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829930"
---
# <a name="skype-for-business-servermodify-sip-trunk-configuration-settings"></a>Skype for Business ServerModify SIP trunk configuration settings

Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. Queste impostazioni consentono di specificare quanto segue:

- Se abilitare il bypass multimediale nei trunk.
- Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).
- Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).

Quando si installa Skype for Business Server, viene creata automaticamente una raccolta globale di impostazioni di configurazione trunk SIP. Gli amministratori inoltre possono creare raccolte di impostazioni personalizzate nell'ambito del sito o del servizio (solo per il servizio gateway PSTN). Una qualsiasi di queste raccolte può essere modificata in un secondo momento utilizzando Skype for Business Server pannello di controllo o Windows PowerShell.

Quando si modificano le impostazioni di configurazione dei trunk SIP utilizzando il Pannello di controllo Skype for Business Server Server, sono disponibili le opzioni seguenti:

|Impostazione dell'interfaccia utente |Parametro di PowerShell |Descrizione |
|--|--|--|
|Nome|Identità|Identificatore univoco della raccolta. È una proprietà di sola lettura; non è possibile modificare l'identitià di una raccolta di impostazioni di configurazione per il trunk.|
|Descrizione|Descrizione|Consente agli amministratori di archiviare informazioni aggiuntive sulle impostazioni (ad esempio, le finalità della configurazione del trunk).|
|Dialoghi anticipati massimi supportati|MaxEarlyDialogs|Il numero massimo di risposte instradate che un gateway PSTN, IP-PBX o SBC nel provider di servizi può ricevere per un invito inviato a Mediation Server.|
|Livello di supporto della crittografia|SRTPMode|Indica il livello di supporto per la protezione del traffico multimediale tra Mediation Server e il gateway PSTN, il sistema IP-PBX o il servizio SBC nel provider dei servizi. Nel caso del bypass multimediale, questo valore deve essere compatibile con l'impostazione di EncryptionLevel nella configurazione degli elementi multimediali. La configurazione multimediale viene impostata utilizzando i cmdlet New-CsMediaConfiguration e Set-CsMediaConfiguration.Media configuration is set by using the New-CsMediaConfiguration and Set-CsMediaConfiguration cmdlet.<br/>I valori consentiti sono:<br/><br/>**Obbligatorio:** è necessario utilizzare la crittografia SRTP.<br/>**Facoltativo:** verrà utilizzato SRTP se il gateway lo supporta.<br/>**Non supportato:** la crittografia SRTP non è supportata e pertanto non verrà utilizzata.<br/><br/>SRTPMode viene utilizzato solo se il gateway è configurato per l'uso di TLS (Transport Layer Security). Se il gateway è configurato con il protocollo TCP (Transmission Control Protocol) per il trasporto, SRTPMode viene impostato internamente su NotSupported.|
|Supporto riferimento|Enable3pccRefer<br/>EnableReferSupport|Se impostato su **Abilita l'invio del riferimento al gateway**, indica che il trunk supporta ricezione di richieste Refer da Mediation Server.<br/>Se impostato su **Abilita il riferimento usando il controllo delle chiamate di terze parti**, indica che il protocollo 3pcc può essere utilizzato per consentire alle chiamate trasferite di eseguire il bypass del sito ospitato. Il protocollo 3pcc è noto anche come "controllo delle terze parti," e si verifica quando si utilizza una terza parte per la connessione a una coppia di chiamanti (ad esempio, un operatore che connette una chiamata dall'utente A all'utente B).|
|Abilita bypass multimediale|EnableBypass|Indica se il bypass multimediale è abilitato per questo trunk. È possibile abilitare il bypass multimediale solo se è abilitato anche **Elaborazione multimediale centralizzata**.|
|Elaborazione multimediale centralizzata|ConcentrateTopology|Indica se esiste un punto di terminazione multimediale noto. Un esempio di punto di terminazione multimediale noto può essere costituito da un gateway PSTN in cui la terminazione dei supporti ha lo stesso IP della terminazione dei segnali.|
|Abilita scatto RTP|EnableRTPLatching|Indica se i trunk SIP supportano lo scatto RTP, una tecnologia che abilita la connettività RTP/RTCP attraverso un dispositivo NAT o firewall.|
|Abilita inoltro cronologia chiamate|ForwardCallHistory|Indica se le informazioni relative alla cronologia delle chiamate saranno inoltrate attraverso il trunk.|
|Abilita inoltro dati PAI|ForwardPAI|Indica se l'intestazione PAI sarà inoltrata con la chiamata. L'intestazione PAI consente di identificare l'identità del chiamante.|
|Abilita timer di failover del routing in uscita|EnableFastFailoverTimer|Indica se le chiamate non risposte dal entro 10 secondi saranno instradate al primo trunk disponibile; se non esistono altri trunk, la chiamata sarà ignorata. In un'organizzazione con reti e risposte del gateway lente, ciò potrebbe portare a ignorare chiamate non volutamente.|
|Utilizzo PSTN associato|PSTNUsages|Raccolta di utilizzi PSTN assegnati al trunk.|
|Numero convertito da testare|N/D|Numero di telefono che può essere utilizzato per un test ad hoc delle impostazioni di configurazione del trunk.|
|Regole di conversione associate|OutboundTranslationRulesList|Raccolta di regole di conversione dei numeri di telefono che si applicano alle chiamate gestite mediante il routing in uscita (chiamate instradate a destinazioni PBX o PSTN).|
|Regole di conversione del numero chiamato|OutboundCallingNumberTranslationRulesList|Raccolta di regole di conversione del numero chiamato in uscita, assegnate al trunk.|
|Numero di telefono da testare.|N/D|Numero di telefono che può essere utilizzato per un test ad hoc delle regole di conversione.|
|Numero di chiamata|N/D|Indica che il numero di telefono da testare è il numero di telefono del chiamante.|
|Numero chiamato|N/D|Indica che il numero di telefono da testare è il numero di telefono della persona che riceve la chiamata.|
|||

> [!Note]
> I Skype for Business Server CsTrunkConfiguration supportano proprietà aggiuntive non visualizzate nel Pannello Skype for Business Server controllo. Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsTrunkConfiguration.](/powershell/module/skype/Set-CsTrunkConfiguration) 

**Per modificare le impostazioni di configurazione dei trunk SIP tramite il Skype for Business Server pannello di controllo**

1. Nel Pannello Skype for Business Server di controllo fare clic su **Routing vocale** e quindi su **Configurazione trunk.**
2. Nella scheda **Configurazione trunk** fare doppio clic sulle impostazioni di configurazione del trunk che si desidera modificare. È possibile modificare una sola raccolta di impostazioni per volta. Per apportare le stesse modifiche a più raccolte, utilizzare Windows PowerShell.
3. Nella finestra **di dialogo Modifica configurazione** trunk effettuare le selezioni appropriate e quindi fare clic su **OK.**
4. La proprietà Stato per la raccolta verrà aggiornata a Commit non eseguito. Per confermare le modifiche ed eliminare la raccolta, fare clic su **Commit** e quindi su **Commit tutto.**
5. Nella finestra **di dialogo Impostazioni di** configurazione vocale di cui non è stato eseguito ilcommitted fare clic su **OK.**
6. Nella finestra **Skype for Business Server pannello** di controllo fare clic su **OK.**
