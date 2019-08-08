---
title: Creare una nuova raccolta di impostazioni di configurazione trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
description: 'Riepilogo: informazioni su come creare una nuova raccolta di impostazioni di configurazione trunk usando il pannello di controllo di Skype for Business Server.'
ms.openlocfilehash: f724526f35a530c19e709e7faa62369e454ea6a4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240302"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>Creare una nuova raccolta di impostazioni di configurazione trunk in Skype for Business Server 

**Riepilogo:** Informazioni su come creare una nuova raccolta di impostazioni di configurazione trunk usando il pannello di controllo di Skype for Business Server.
  
Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch eXchange) o un SBC (Session Border Controller) presso il provider di servizi. Queste impostazioni eseguono operazioni come specifica:
  
- Se il bypass multimediale deve essere abilitato nei trunk.
    
- Condizioni in cui vengono inviati i pacchetti RTCP (Realtime Transport Control Protocol).
    
- Indipendentemente dal fatto che sia necessaria o meno la crittografia SRTP (Secure Realtime Transport Protocol) in ogni trunk.
    
Quando si installa Skype for Business Server, viene creata una raccolta globale di impostazioni di configurazione trunk SIP. Gli amministratori possono inoltre creare raccolte di impostazioni personalizzate nell'ambito del sito o nell'ambito del servizio (solo per il servizio gateway PSTN).
  
Quando si creano le impostazioni di configurazione del trunk SIP tramite il pannello di controllo di Skype for Business Server, le opzioni seguenti sono disponibili.
  
|**Impostazione dell'interfaccia utente**|**Parametro di PowerShell**|**Descrizione**|
|:-----|:-----|:-----|
|Nome  <br/> |Identity  <br/> |Identificatore univoco per la raccolta. Questa proprietà è di sola lettura; non è possibile modificare l'identità di una raccolta di impostazioni di configurazione trunk.  <br/> |
|Descrizione  <br/> |Descrizione  <br/> |Consente agli amministratori di archiviare informazioni di aggiunta sulle impostazioni, ad esempio lo scopo della configurazione trunk.  <br/> |
|Finestre di dialogo iniziali massime supportate  <br/> |MaxEarlyDialogs  <br/> |Numero massimo di risposte a forcella un gateway PSTN, IP-PBX o SBC presso il provider di servizi può ricevere un invito inviato al Mediation Server.  <br/> |
|Livello di supporto della crittografia  <br/> |SRTPMode  <br/> | Indica il livello di supporto per la protezione del traffico multimediale tra il Mediation Server e il gateway PSTN, IP-PBX o SBC presso il provider di servizi. Nel caso del bypass multimediale, questo valore deve essere compatibile con l'impostazione di EncryptionLevel nella configurazione degli elementi multimediali. La configurazione multimediale viene impostata usando i cmdlet [New-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmediaconfiguration?view=skype-ps) e [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps) . <br/>  I valori consentiti sono: <br/>  Obbligatorio: è necessario usare la crittografia SRTP. <br/>  Facoltativo: SRTP verrà usato se il gateway lo supporta. <br/>  Non supportata: la crittografia SRTP non è supportata e pertanto non verrà usata. <br/>  SRTPMode viene usato solo se il gateway è configurato per l'uso di Transport Layer Security (TLS). Se il gateway è configurato con il protocollo TCP (Transmission Control Protocol) come trasporto, SRTPMode è impostato internamente su non supportato. <br/> |
|Fare riferimento al supporto  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |Se impostato per **abilitare l'invio, fare riferimento al gateway**, indica che il trunk supporta la ricezione di richieste di riferimento dal server Mediation.  <br/> Se impostato per **abilitare l'opzione fai riferimento tramite il controllo delle chiamate di terze parti**, indica che il protocollo 3PCC può essere usato per consentire alle chiamate trasferite di ignorare il sito ospitato. 3PCC è anche noto come "controllo di terze parti" e si verifica quando viene usata una terza parte per connettere una coppia di chiamanti (ad esempio, un operatore che effettua una chiamata dalla persona a alla persona B).  <br/> |
|Abilitare il bypass multimediale  <br/> |EnableBypass  <br/> |Indica se il bypass multimediale è abilitato per il trunk. Il bypass multimediale può essere abilitato solo se è abilitata anche l' **elaborazione media centralizzata** . <br/> |
|Elaborazione multimediale centralizzata  <br/> |ConcentratedTopology  <br/> |Indica se è presente un punto di interruzione multimediale noto. Un esempio di punto di terminazione multimediale noto può essere costituito da un gateway PSTN in cui la terminazione degli elementi multimediali ha lo stesso IP della terminazione dei segnali.  <br/> |
|Abilitare l'aggancio RTP  <br/> |EnableRTPLatching  <br/> |Indica se i trunk SIP supportano o meno il latching RTP. Il latching RTP è una tecnologia che consente la connettività RTP/RTCP tramite un dispositivo NAT (Network Address Translator) o un firewall.  <br/> |
|Abilitare la cronologia delle chiamate inoltrate  <br/> |ForwardCallHistory  <br/> |Indica se le informazioni del registro chiamate verranno inoltrate tramite il trunk.  <br/> |
|Abilitare inoltra P-asserzione-dati identità  <br/> |ForwardPAI  <br/> |Indica se l'intestazione PAI (P-Asserted-Identity) verrà inoltrata insieme alla chiamata. L'intestazione PAI consente di verificare l'identità del chiamante.  <br/> |
|Abilitare il timer di failover del routing in uscita  <br/> |EnableFastFailoverTimer  <br/> |Indica se le chiamate in uscita non risposte dal gateway entro 10 secondi verranno instradate al successivo trunk disponibile. Se non ci sono trunk aggiuntivi, la chiamata verrà eliminata automaticamente. In un'organizzazione con reti lente e risposte del gateway, che potrebbero potenzialmente causare la perdita di chiamate inutilmente.  <br/> |
|Usi PSTN associati  <br/> |PSTNUsages  <br/> |Raccolta di utilizzi PSTN assegnati al trunk.  <br/> |
|Numero tradotto da testare  <br/> |N/D  <br/> |Numero di telefono che può essere usato per eseguire un test ad hoc delle impostazioni di configurazione del trunk.  <br/> |
|Regole di traduzione associate  <br/> |OutboundTranslationRulesList  <br/> |Raccolta di regole di traduzione per i numeri di telefono che si applicano alle chiamate gestite dal routing in uscita (chiamate indirizzate a destinazioni PBX o PSTN).  <br/> |
|Regole di traduzione del numero chiamate  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |Raccolta di regole di conversione dei numeri in uscita assegnate al trunk.  <br/> |
|Numero di telefono da testare  <br/> |N/D  <br/> |Numero di telefono che può essere usato per eseguire un test ad hoc sulle regole di traduzione.  <br/> |
|Numero chiamante  <br/> |N/D  <br/> |Indica che il numero di telefono da testare è il numero di telefono del chiamante.  <br/> |
|Numero chiamato  <br/> |N/D  <br/> |Indica che il numero di telefono da testare è il numero di telefono della persona che viene chiamata.  <br/> |
   
> [!NOTE]
> I cmdlet di Skype for Business Server CsTrunkConfiguration supportano altre proprietà non visualizzate nel pannello di controllo di Skype for Business Server. Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cstrunkconfiguration?view=skype-ps) .
  
### <a name="to-create-new-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Per creare nuove impostazioni di configurazione trunk tramite il pannello di controllo di Skype for Business Server

1. Nel pannello di controllo di Skype for Business Server fare clic su **routing vocale**e quindi su **configurazione trunk**.
    
2. Nella scheda **configurazione trunk** fare clic su **nuovo**e quindi su **Trunk sito** per creare le nuove impostazioni nell'ambito del sito o trunk del **pool** per creare le nuove impostazioni nell'ambito del servizio.
    
3. Nella finestra di dialogo **Seleziona un sito** o **Seleziona un servizio** (la finestra di dialogo visualizzata dipende dal fatto che si stiano creando impostazioni con ambito del sito o con ambito servizio) selezionare la posizione per le nuove impostazioni di configurazione e quindi fare clic su **OK** . . Se la finestra di dialogo è vuota, significa che non è disponibile alcuna posizione per creare le nuove impostazioni. ad esempio, se la finestra di dialogo **Seleziona sito** è vuota, significa che tutti i siti sono già stati assegnati a una raccolta di siti di configurazione trunk e ogni sito (e ogni servizio) può ospitare solo una di queste raccolte. In questo caso, puoi eliminare la raccolta esistente e creare una nuova raccolta oppure semplicemente modificare la raccolta esistente.
    
4. Nella finestra di dialogo **nuova configurazione trunk** eseguire le selezioni appropriate e quindi fare clic su **OK**.
    
5. La proprietà **state** per la raccolta verrà aggiornata in UNCOMMITTED. **** Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **commit** e quindi su **commit tutti**.
    
6. Nella finestra di dialogo **impostazioni di configurazione vocale** non impegnata fare clic su **OK**.
    
7. Nella finestra di dialogo **Pannello di controllo di Skype for Business Server** fare clic su **OK**.
    

