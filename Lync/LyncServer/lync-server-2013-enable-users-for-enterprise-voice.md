---
title: 'Lync Server 2013: consentire agli utenti di VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d94b2ad348bc1d086716deed2beef0dcfbe78e2b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>Consentire agli utenti di VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Dopo aver installato i file per uno o più server di mediazione, configurare il routing delle chiamate in uscita e, facoltativamente, distribuire una o più funzionalità vocali avanzate per l'organizzazione, è possibile usare le procedure seguenti per consentire a un utente di effettuare chiamate tramite VoIP aziendale:

<div>


> [!NOTE]  
> Delle procedure seguenti, solo il primo può essere eseguito usando il pannello di controllo di Lync Server. Per le procedure rimanenti, è possibile usare solo Lync Server Management Shell.



</div>

  - Abilitare l'account utente per VoIP aziendale.

  - Opzionale Assegnare l'account utente a un criterio vocale specifico per l'utente.

  - Opzionale Assegna l'account utente a un dial plan specifico per l'utente.

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>Per abilitare un account utente per VoIP aziendale

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **utenti**.

4.  Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si vuole abilitare e quindi fare clic su **trova**.

5.  Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.

6.  Nel menu **modifica** fare clic su **Mostra dettagli**.

7.  Nella pagina **modifica utente di Lync Server** , in **telefonia**, fare clic su **VoIP aziendale**.

8.  Fare clic su **URI linea**e quindi digitare un numero di telefono normalizzato univoco, ad esempio Tel: + 14255550200.

9.  Fare clic su **Commit**.

Per completare l'abilitazione di un utente per VoIP aziendale, assicurati che all'utente sia assegnato un criterio vocale e un dial plan, sia globale (assegnato per impostazione predefinita) che specifico per l'utente.

Per impostazione predefinita, a tutti gli utenti viene assegnato un criterio vocale globale e un dial plan. Se un criterio vocale o un dial plan esiste a livello di sito per il sito in cui si trova l'account utente, i criteri del sito verranno applicati automaticamente all'utente. Per applicare un criterio vocale per utente o un dial plan a un utente, è necessario eseguire i cmdlet **Grant-CsVoicePolicy** e **Grant-CsDialPlan** . Per informazioni dettagliate, vedere la documentazione di [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

<div>

## <a name="voice-policy-assignment"></a>Assegnazione dei criteri vocali

I criteri vocali globali e a livello di sito vengono assegnati automaticamente a tutti gli account utente abilitati per VoIP aziendale. È anche possibile creare criteri vocali applicabili a utenti o gruppi specifici. Questi criteri per utente devono essere assegnati in modo esplicito agli utenti o ai gruppi. Se si vuole usare il criterio vocale globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione e continuare la sezione Assegnazione di dial plan più avanti in questo argomento.

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>Per assegnare un criterio vocale specifico per l'utente

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Per assegnare un criterio vocale utente esistente a un utente, eseguire le operazioni seguenti al prompt dei comandi:
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    Ad esempio:
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    In questo esempio l'utente con il nome visualizzato Bob Kelly viene assegnato il criterio vocale con il nome **VoicePolicyJapan**.

Per informazioni dettagliate sull'assegnazione di un criterio vocale specifico per l'utente o sull'uso del cmdlet **Grant-CsVoicePolicy** , vedere la documentazione di [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>Assegnazione di dial plan

Per completare la configurazione dell'account utente per gli utenti di VoIP aziendale o per gli utenti di servizi di conferenza telefonica con accesso esterno, l'utente deve essere assegnato a un dial plan. Gli account utente useranno automaticamente il dial plan globale o, se disponibile, il dial plan a livello di sito, quando non si assegna esplicitamente un dial plan per utente esistente. Se si vuole usare il dial plan globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione.

<div>

## <a name="to-assign-a-dial-plan"></a>Per assegnare un dial plan

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Per assegnare un dial plan specifico per l'utente, eseguire la procedura seguente al prompt dei comandi:
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    Ad esempio:
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    In questo esempio l'utente con il nome visualizzato Bob Kelly viene assegnato al dial plan utente con il nome **DialPlanJapan**.

Per informazioni dettagliate sull'assegnazione di un dial plan utente o sull'esecuzione del cmdlet **Grant-CsDialPlan** , vedere la documentazione di [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Disabilitare un utente per VoIP aziendale in Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

