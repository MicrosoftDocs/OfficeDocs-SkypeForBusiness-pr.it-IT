---
title: 'Lync Server 2013: abilitare gli utenti per VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c48f701f9396c43337e2723f0dc83a8eda8d96ee
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a>Abilitare gli utenti per VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Dopo aver installato i file per uno o più Mediation Server, configurare il routing delle chiamate in uscita e, facoltativamente, distribuire una o più funzionalità di VoIP aziendale avanzate, è possibile utilizzare le procedure seguenti per consentire a un utente di effettuare chiamate tramite VoIP aziendale:

<div>


> [!NOTE]  
> Nelle procedure riportate di seguito, solo il primo può essere eseguito utilizzando il pannello di controllo di Lync Server. Per le procedure rimanenti, è possibile utilizzare solo Lync Server Management Shell.



</div>

  - Abilitare l'account utente per VoIP aziendale.

  - (Facoltativo) Assegnare all'account utente criteri vocali specifici dell'utente.

  - (Facoltativo) Assegnare all'account utente un dial plan specifico dell'utente.

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a>Per abilitare un account utente per VoIP aziendale

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti**.

4.  Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account di Gestione account di protezione, dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente da abilitare e quindi fare clic su **Trova**.

5.  Nella tabella fare clic sull'account utente che si desidera abilitare per VoIP aziendale.

6.  Scegliere **Mostra dettagli** dal menu **Modifica**.

7.  Nella pagina **Modifica utente Lync Server**, in **Telefonia**, fare clic su **VoIP aziendale**.

8.  Fare clic su **URI linea** e quindi digitare un numero di telefono normalizzato univoco, ad esempio tel:+14255550200.

9.  Fare clic su **Commit**.

Per completare l'abilitazione di un utente per VoIP aziendale, assicurarsi che all'utente sia assegnato un criterio vocale e un dial plan, indipendentemente dal fatto che sia globale (assegnato per impostazione predefinita) o specifico dell'utente.

Per impostazione predefinita, tutti gli utenti vengono assegnati a criteri vocali e dial plan globali. Se nel sito principale dell'utente esistono criteri vocali o un dial plan a livello di sito, i criteri del sito verranno applicati automaticamente all'utente. Per applicare criteri vocali o un dial plan per utente, è necessario eseguire i cmdlet **Grant-CsVoicePolicy** e **Grant-CsDialPlan**. Per informazioni dettagliate, vedere la documentazione di [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

<div>

## <a name="voice-policy-assignment"></a>Assegnazione di criteri vocali

I criteri vocali globali e a livello di sito vengono assegnati automaticamente a tutti gli account utente abilitati per VoIP aziendale. È inoltre possibile creare criteri vocali applicabili a utenti o gruppi specifici. Questi criteri per utente devono essere assegnati esplicitamente agli utenti o ai gruppi. Se si desidera utilizzare il criterio vocale globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione e continuare con la sezione Assegnazione dial plan più avanti in questo argomento.

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a>Per assegnare criteri vocali specifici dell'utente

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Per assegnare un criterio vocale esistente a un utente, eseguire quanto segue al prompt dei comandi:
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    Esempio:
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    In questo esempio, all'utente con il nome visualizzato Bob Kelly viene assegnato il criterio vocale con il nome **VoicePolicyJapan**.

Per informazioni dettagliate sull'assegnazione di criteri vocali specifici dell'utente o sull'esecuzione del cmdlet **Grant-CsVoicePolicy** , vedere la documentazione di [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a>Assegnazione di dial plan

Per completare la configurazione degli account per gli utenti di VoIP aziendale o per gli utenti delle conferenze telefoniche con accesso esterno, è necessario che all'utente sia assegnato un dial plan. Gli account utente utilizzeranno automaticamente il dial plan globale oppure, se disponibile, il dial plan a livello di sito se non si assegna esplicitamente un dial plan per utente. Se si desidera utilizzare il dial plan globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione.

<div>

## <a name="to-assign-a-dial-plan"></a>Per assegnare un dial plan

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Per assegnare un dial plan specifico dell'utente, al prompt dei comandi eseguire quanto segue:
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    Ad esempio:
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    In questo esempio, all'utente con il nome visualizzato Bob Kelly viene assegnato il dial plan utente con il nome **DialPlanJapan**.

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

