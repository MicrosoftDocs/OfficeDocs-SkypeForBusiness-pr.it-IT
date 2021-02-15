---
title: Modificare le impostazioni di configurazione dei trunk SIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
description: 'Riepilogo: informazioni su come modificare le impostazioni di configurazione dei trunk SIP utilizzando il Pannello di controllo di Skype for Business Server.'
ms.openlocfilehash: 43d32e04716423578173d7eed412445f196f9b65
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830776"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Modificare le impostazioni di configurazione dei trunk SIP in Skype for Business Server
 
**Riepilogo:** Informazioni su come modificare le impostazioni di configurazione dei trunk SIP utilizzando il Pannello di controllo di Skype for Business Server.
  
Le impostazioni di configurazione dei trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un IP-Public Branch eXchange (PBX) o un session border controller (SBC) presso il provider di servizi. Queste impostazioni consentono di specificare quanto segue:
  
- Se abilitare il bypass multimediale nei trunk.
    
- Condizioni in cui vengono inviati i pacchetti RTCP (Realtime Transport Control Protocol).
    
- Indica se è necessaria o meno la crittografia SRTP (Secure Realtime Transport Protocol) in ogni trunk.
    
Quando si installa Skype for Business Server, viene creata automaticamente una raccolta globale di impostazioni di configurazione dei trunk SIP. Gli amministratori inoltre possono creare raccolte di impostazioni personalizzate nell'ambito del sito o del servizio (solo per il servizio gateway PSTN). Una qualsiasi di queste raccolte può essere successivamente modificata utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
Quando si modificano le impostazioni di configurazione dei trunk SIP utilizzando il Pannello di controllo di Skype for Business Server, sono disponibili le opzioni seguenti.
  
|**Impostazione dell'interfaccia utente**|**Parametro di PowerShell**|**Descrizione**|
|:-----|:-----|:-----|
|Nome  <br/> |Identità  <br/> |Identificatore univoco della raccolta. È una proprietà di sola lettura; non è possibile modificare l'identitià di una raccolta di impostazioni di configurazione per il trunk.  <br/> |
|Descrizione  <br/> |Descrizione  <br/> |Consente agli amministratori di archiviare informazioni aggiuntive sulle impostazioni (ad esempio, le finalità della configurazione del trunk).  <br/> |
|Dialoghi anticipati massimi supportati  <br/> |MaxEarlyDialogs  <br/> |Il numero massimo di risposte instradate che un gateway PSTN, IP-PBX o SBC nel provider di servizi può ricevere per un invito inviato a Mediation Server.  <br/> |
|Livello di supporto della crittografia  <br/> |SRTPMode  <br/> | Indica il livello di supporto per la protezione del traffico multimediale tra Mediation Server e il gateway PSTN, il sistema IP-PBX o il servizio SBC nel provider dei servizi. Nel caso del bypass multimediale, questo valore deve essere compatibile con l'impostazione di EncryptionLevel nella configurazione degli elementi multimediali. La configurazione multimediale viene impostata utilizzando i cmdlet [New-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmediaconfiguration?view=skype-ps) e [Set-CsMediaConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps) <br/>  I valori consentiti sono: <br/>  Obbligatorio: è necessario utilizzare la crittografia SRTP. <br/>  Facoltativo: SRTP verrà utilizzato se supportato dal gateway. <br/>  Non supportato: la crittografia SRTP non è supportata, pertanto non verrà utilizzata. <br/>  SRTPMode viene utilizzato solo se il gateway è configurato per l'uso di TLS (Transport Layer Security). Se il gateway è configurato con il protocollo TCP (Transmission Control Protocol) per il trasporto, SRTPMode viene impostato internamente su NotSupported.<br/> |
|Supporto riferimento  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |Se impostato su **Abilita l'invio del riferimento al gateway**, indica che il trunk supporta ricezione di richieste Refer da Mediation Server.  <br/> Se impostato su **Abilita il riferimento usando il controllo delle chiamate di terze parti**, indica che il protocollo 3pcc può essere utilizzato per consentire alle chiamate trasferite di eseguire il bypass del sito ospitato. Il protocollo 3pcc è noto anche come "controllo delle terze parti," e si verifica quando si utilizza una terza parte per la connessione a una coppia di chiamanti (ad esempio, un operatore che connette una chiamata dall'utente A all'utente B).<br/> |
|Abilita bypass multimediale  <br/> |EnableBypass  <br/> |Indica se il bypass multimediale è abilitato per questo trunk. È possibile abilitare il bypass multimediale solo se è abilitato anche **Elaborazione multimediale centralizzata**.<br/> |
|Elaborazione multimediale centralizzata  <br/> |Consod.1  <br/> |Indica se esiste un punto di terminazione multimediale noto. Un esempio di punto di terminazione multimediale noto può essere costituito da un gateway PSTN in cui la terminazione dei supporti ha lo stesso IP della terminazione dei segnali.  <br/> |
|Abilita scatto RTP  <br/> |EnableRTPLatching  <br/> |Indica se i trunk SIP supportano lo scatto RTP, una tecnologia che abilita la connettività RTP/RTCP attraverso un dispositivo NAT o firewall.  <br/> |
|Abilita inoltro cronologia chiamate  <br/> |ForwardCallHistory  <br/> |Indica se le informazioni relative alla cronologia delle chiamate saranno inoltrate attraverso il trunk.  <br/> |
|Abilita inoltro dati PAI  <br/> |ForwardPAI  <br/> |Indica se l'intestazione PAI sarà inoltrata con la chiamata. L'intestazione PAI consente di identificare l'identità del chiamante.  <br/> |
|Abilita timer di failover del routing in uscita  <br/> |EnableFastFailoverTimer  <br/> |Indica se le chiamate non risposte dal entro 10 secondi saranno instradate al primo trunk disponibile; se non esistono altri trunk, la chiamata sarà ignorata. In un'organizzazione con reti e risposte del gateway lente, ciò potrebbe portare a ignorare chiamate non volutamente.  <br/> |
|Utilizzo PSTN associato  <br/> |PSTNUsages  <br/> |Raccolta di utilizzi PSTN assegnati al trunk.  <br/> |
|Numero convertito da testare  <br/> |N/D  <br/> |Numero di telefono che può essere utilizzato per un test ad hoc delle impostazioni di configurazione del trunk.  <br/> |
|Regole di conversione associate  <br/> |OutboundTranslationRulesList  <br/> |Raccolta di regole di conversione dei numeri di telefono che si applicano alle chiamate gestite mediante il routing in uscita (chiamate instradate a destinazioni PBX o PSTN).  <br/> |
|Regole di conversione del numero chiamato  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |Raccolta di regole di conversione del numero chiamato in uscita, assegnate al trunk.  <br/> |
|Numero di telefono da testare.  <br/> |N/D  <br/> |Numero di telefono che può essere utilizzato per un test ad hoc delle regole di conversione.  <br/> |
|Numero di chiamata  <br/> |N/D  <br/> |Indica che il numero di telefono da testare è il numero di telefono del chiamante.  <br/> |
|Numero chiamato  <br/> |N/D  <br/> |Indica che il numero di telefono da testare è il numero di telefono della persona che riceve la chiamata.  <br/> |
   
> [!NOTE]
> I cmdlet CsTrunkConfiguration di Lync Server supportano proprietà aggiuntive non visualizzate nel Pannello di controllo di Lync Server. Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-cstrunkconfiguration?view=skype-ps)
  
### <a name="to-modify-sip-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Per modificare le impostazioni di configurazione dei trunk SIP utilizzando il Pannello di controllo di Skype for Business Server

1. Nel Pannello di controllo di Skype for Business Server fare clic **su Routing vocale** e quindi su Configurazione **trunk.**
    
2. Nella scheda **Configurazione trunk** fare doppio clic sulle impostazioni di configurazione del trunk che si desidera modificare. È possibile modificare una sola raccolta di impostazioni per volta. Per apportare le stesse modifiche a più raccolte, utilizzare Windows PowerShell.
    
3. Nella finestra **di dialogo Modifica configurazione** trunk effettuare le selezioni appropriate e quindi fare clic su **OK.**
    
4. La proprietà **Stato** per la raccolta verrà aggiornata a **Commit non eseguito**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **Commit**, quindi su **Salva tutto**.
    
5. Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** fare clic su **OK**.
    
6. Nella finestra di dialogo Del Pannello di controllo di **Skype for Business Server** fare clic su **OK.**
    

