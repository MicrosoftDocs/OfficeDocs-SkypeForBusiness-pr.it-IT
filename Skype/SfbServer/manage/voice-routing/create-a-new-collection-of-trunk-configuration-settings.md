---
title: Creare una nuova raccolta di impostazioni di configurazione trunk in Skype for Business Server
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
description: Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi.
ms.openlocfilehash: 849258197c6ce5485126934e60e50d906be1c1b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028857"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>Creare una nuova raccolta di impostazioni di configurazione trunk in Skype for Business Server

Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. Queste impostazioni consentono di specificare quanto segue:
- Se abilitare il bypass multimediale nei trunk.
- Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).
- Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).

Quando si installa Skype for Business Server, viene creata una raccolta globale di impostazioni di configurazione del trunk SIP. Gli amministratori inoltre possono creare raccolte di impostazioni personalizzate nell'ambito del sito o del servizio (solo per il servizio gateway PSTN).

Quando si creano le impostazioni di configurazione del trunk SIP usingSkype per il pannello di controllo di Business Server, sono disponibili le opzioni seguenti:

|Impostazione dell'interfaccia utente | Parametro di PowerShell | Descrizione |
|--|--|--|
|Nome|Identità|Identificatore univoco della raccolta. È una proprietà di sola lettura; non è possibile modificare l'identitià di una raccolta di impostazioni di configurazione per il trunk.|
|Descrizione|Descrizione|Consente agli amministratori di archiviare informazioni aggiuntive sulle impostazioni (ad esempio, le finalità della configurazione del trunk).|
|Dialoghi anticipati massimi supportati|MaxEarlyDialogs|Il numero massimo di risposte instradate che un gateway PSTN, IP-PBX o SBC nel provider di servizi può ricevere per un invito inviato a Mediation Server.|
|Livello di supporto della crittografia|SRTPMode|Indica il livello di supporto per la protezione del traffico multimediale tra Mediation Server e il gateway PSTN, il sistema IP-PBX o il servizio SBC nel provider dei servizi. Nel caso del bypass multimediale, questo valore deve essere compatibile con l'impostazione di EncryptionLevel nella configurazione degli elementi multimediali. La configurazione multimediale viene impostata utilizzando i cmdlet [New-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration) e [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration) .<br/>I valori consentiti sono:<br/><br/>**Obbligatorio**: è necessario utilizzare la crittografia SRTP.<br/>**Facoltativo**: SRTP verrà utilizzato se il gateway lo supporta.<br/>**Non supportato**: la crittografia SRTP non è supportata e pertanto non verrà utilizzata.<br/><br/>SRTPMode viene utilizzato solo se il gateway è configurato per l'uso di TLS (Transport Layer Security). Se il gateway è configurato con il protocollo TCP (Transmission Control Protocol) per il trasporto, SRTPMode viene impostato internamente su NotSupported.|
|Supporto riferimento|Enable3pccRefer<br/>EnableReferSupport|Se impostato su **Abilita l'invio del riferimento al gateway**, indica che il trunk supporta ricezione di richieste Refer da Mediation Server.<br/>Se impostato su **Abilita il riferimento usando il controllo delle chiamate di terze parti**, indica che il protocollo 3pcc può essere utilizzato per consentire alle chiamate trasferite di eseguire il bypass del sito ospitato. Il protocollo 3pcc è noto anche come "controllo delle terze parti," e si verifica quando si utilizza una terza parte per la connessione a una coppia di chiamanti (ad esempio, un operatore che connette una chiamata dall'utente A all'utente B).|
|Abilita bypass multimediale|EnableBypass|Indica se il bypass multimediale è abilitato per questo trunk. È possibile abilitare il bypass multimediale solo se è abilitato anche **Elaborazione multimediale centralizzata**.|
|Elaborazione multimediale centralizzata|ConcentratedTopology|Indica se esiste un punto di terminazione multimediale noto. Un esempio di punto di terminazione multimediale noto può essere costituito da un gateway PSTN in cui la terminazione dei supporti ha lo stesso IP della terminazione dei segnali.|
|Abilita scatto RTP|EnableRTPLatching|Indica se i trunk SIP supportano lo scatto RTP, una tecnologia che abilita la connettività RTP/RTCP attraverso un dispositivo NAT o firewall.|
|Abilita inoltro cronologia chiamate|ForwardCallHistory|Indica se le informazioni relative alla cronologia delle chiamate saranno inoltrate attraverso il trunk.|
|Abilita inoltro dati PAI|ForwardPAI|Indica se l'intestazione PAI sarà inoltrata con la chiamata. L'intestazione PAI consente di identificare l'identità del chiamante.|
|Abilita timer di failover del routing in uscita|EnableFastFailoverTimer|Indica se le chiamate non risposte dal entro 10 secondi saranno instradate al primo trunk disponibile; se non esistono altri trunk, la chiamata sarà ignorata. In un'organizzazione con reti e risposte del gateway lente, ciò potrebbe portare a ignorare chiamate non volutamente.|
|Utilizzo PSTN associato|PSTNUsages|Raccolta di utilizzi PSTN assegnati al trunk.|
|Numero convertito da testare|N/D|Numero di telefono che può essere utilizzato per un test ad hoc delle impostazioni di configurazione del trunk.|
|Regole di conversione associate|OutboundTranslationRulesList|Raccolta di regole di conversione dei numeri di telefono che si applicano alle chiamate gestite mediante il routing in uscita (chiamate instradate a destinazioni PBX o PSTN).|
|Regole di conversione del numero chiamato|OutboundCallingNumberTranslationRulesList|Raccolta di regole di conversione del numero chiamato in uscita, assegnate al trunk.|
|Numero di telefono da testare.|N/D|Numero di telefono che può essere utilizzato per un test ad hoc delle regole di conversione.|
|Numero di chiamata|N/D|Numero di telefono che può essere utilizzato per un test ad hoc delle regole di conversione.|
|Numero chiamato|N/D|Indica che il numero di telefono da testare è il numero di telefono della persona che riceve la chiamata.|
||||

> [!Note]
> I cmdlet di CsTrunkConfiguration per Skype for Business Server supportano altre proprietà non visualizzate nel pannello di controllo di Skype for Business Server. Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration) . 

**Per creare nuove impostazioni di configurazione del trunk tramite il pannello di controllo di Skype for Business Server**

1. Nel pannello di controllo di Skype for Business Server fare clic su **routing vocale**e quindi su **configurazione trunk**.
2. Nella scheda **configurazione trunk** fare clic su **nuovo**e quindi su **trunk del sito** per creare le nuove impostazioni nell'ambito del sito o **trunk del pool** per creare le nuove impostazioni nell'ambito del servizio.
3. Nella finestra di dialogo **Seleziona un sito** o **Seleziona un servizio** (la finestra di dialogo visualizzata dipenderà dalla creazione di impostazioni con ambito di sito o di servizio), selezionare il percorso per le nuove impostazioni di configurazione e quindi fare clic su **OK**. Se la finestra di dialogo è vuota, significa che non è disponibile alcun posto in cui creare le nuove impostazioni. ad esempio, se la finestra di dialogo **Seleziona un sito** è vuota, significa che a tutti i siti è già stata assegnata una raccolta di siti di configurazione trunk e ogni sito (e ogni servizio) può ospitare solo una raccolta di questo tipo. In tal caso, è possibile eliminare l'insieme esistente e creare una nuova raccolta oppure modificare semplicemente la raccolta esistente.
4. Nella finestra di dialogo **nuova configurazione trunk** , effettuare le selezioni appropriate e quindi fare clic su **OK**.
5. La proprietà **Stato** per la raccolta verrà aggiornata a **Commit non eseguito**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **Commit**, quindi su **Salva tutto**.
6. Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** fare clic su **OK**.
7. Nella finestra di dialogo del **Pannello di controllo di Skype for business** , fare clic su **OK**.
