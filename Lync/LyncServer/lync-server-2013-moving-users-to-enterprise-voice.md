---
title: 'Lync Server 2013: Spostamento di utenti in VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e92f0a7d71d42d8551a51028afec209e795941d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>Spostamento di utenti in VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

Se si stanno spostando gli utenti da un'infrastruttura di telefonia PBX esistente a VoIP aziendale, il processo di distribuzione include alcuni passaggi che non fanno parte del processo di pianificazione già descritto in [pianificazione di VoIP aziendale in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md). Per informazioni sulla migrazione degli utenti da una distribuzione di VoIP aziendale precedente, vedere i documenti di migrazione inclusi nel supporto di installazione.

Il processo di spostamento degli utenti da un'infrastruttura di telefonia esistente a VoIP aziendale è costituito dai passaggi seguenti:

1.  Designare i numeri di telefono primari.

2.  Consentire agli utenti di VoIP aziendale.

3.  Preparare i dial plan per gli utenti.

4.  Pianificare i criteri vocali per l'utente.

5.  Pianificare le route di chiamata.

6.  Configurare PBX o trunk SIP per reindirizzare le chiamate per gli utenti abilitati per VoIP aziendale.

7.  Consente di trasferire gli utenti alla messaggistica unificata di Exchange (scelta consigliata).

Questo argomento descrive la pianificazione necessaria per ognuno di questi passaggi.

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>Passaggio 1. Designare i numeri di telefono primari

Enterprise Voice integra la voce con altri elementi multimediali di messaggistica, in modo che quando una chiamata in arrivo arriva al server, il server esegue il mapping del numero all'URI SIP dell'utente e quindi biforca la chiamata a tutti gli endpoint client associati all'URI SIP. Questo processo richiede che ogni utente sia associato a un numero di telefono principale.

Un numero di telefono principale deve essere:

  - Univoco globale o, nel caso di estensioni interne, univoco nell'organizzazione.

  - Di proprietà e instradabile nell'organizzazione. I numeri personali non devono essere usati.

Gli utenti aziendali possono avere due o più numeri di telefono elencati in servizi di dominio Active Directory. Tutti i numeri di telefono associati a un determinato utente possono essere visualizzati o modificati nella finestra delle proprietà dell'utente nello snap-in utenti e computer di Active Directory.

La casella **numero di telefono** nella scheda **generale** della finestra di dialogo **proprietà utente** deve contenere il numero di lavoro principale dell'utente. Questo numero viene in genere designato come numero di telefono principale dell'utente.

Alcuni utenti possono avere esigenze particolari (ad esempio, un dirigente che vuole che tutte le chiamate in arrivo vengano instradate tramite un assistente amministrativo), ma queste eccezioni dovrebbero essere limitate solo a quelle in cui il bisogno è chiaro e critico.

Dopo aver scelto un numero primario, deve essere:

  - Normalizzato in formato E. 164, ove possibile.

  - Copiato nell'attributo **msRTCSIP-line** di Active Directory.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Coesistenza con il controllo delle chiamate remote (RCC)</STRONG><BR>RCC è la possibilità di usare Lync Server per monitorare e controllare un telefono PBX desktop. Il controllo viene instradato attraverso il server, che funge da gateway per il PBX. Anche se non è possibile configurare un utente per le chiamate RCC e VoIP aziendale, l'impostazione URI linea designa il numero di telefono principale di un utente in entrambi i casi.<BR>Se si vuole che gli utenti selezionati continuino a usare un'infrastruttura PBX esistente, è possibile introdurre l'opzione VoIP aziendale in modo incrementale nell'organizzazione. Per informazioni dettagliate su questo scenario di distribuzione, vedere <A href="lync-server-2013-direct-sip-deployment-options.md">Opzioni di distribuzione SIP dirette in Lync Server 2013</A> nella documentazione relativa alla pianificazione.<BR>Nelle versioni precedenti è possibile abilitare sia RCC che VoIP aziendale per un utente, ma solo se è stato configurato anche l'utente per il forking duale, una caratteristica in cui una chiamata in arrivo suonerà contemporaneamente il telefono PBX e il Communicator di un utente. In Lync Server 2010 la doppia forcella non è supportata.

    
    </div>

Esistono tre metodi per la compilazione dell'attributo **msRTCSIP-line** :

  - Microsoft Identity Integration Server (scelta consigliata)

  - Pagina **utenti** nel pannello di controllo di Lync Server

Dove devono essere elaborati molti numeri di telefono, uno script personalizzato sviluppato dall'organizzazione è la scelta migliore. In base al modo in cui l'organizzazione rappresenta i numeri di telefono in servizi di dominio Active Directory, è possibile che lo script debba normalizzare i numeri di telefono primari in formato E. 164 prima di copiarli nell'attributo **msRTCSIP-line** .

  - Se l'organizzazione mantiene tutti i numeri di telefono in servizi di dominio Active Directory in un unico formato e se tale formato è E. 164, lo script deve solo scrivere ogni numero di telefono principale nell'attributo **msRTCSIP-line** .

  - Se l'organizzazione mantiene tutti i numeri di telefono in servizi di dominio Active Directory in un unico formato, ma tale formato non è E. 164, lo script deve definire una regola di normalizzazione appropriata per convertire i numeri di telefono primari dal formato esistente in E. 164 prima di scriverli nell'attributo **msRTCSIP-line** .

  - Se l'organizzazione non applica un formato standard per i numeri di telefono in servizi di dominio Active Directory, lo script deve definire le regole di normalizzazione appropriate per convertire i numeri di telefono primari dai vari formati in conformità E. 164 prima di scrivere i numeri di telefono primari nell'attributo **msRTCSIP-line** .

Lo script dovrà anche inserire il prefisso **Tel:** prima di ogni numero primario prima di scriverlo nell'attributo **msRTCSIP-line** .

Il formato previsto del numero specificato in questo attributo è:

  - Tel: + 14255550100; ext = 50100.

  - Tel: 5550100 (per le estensioni esclusive di Enterprise Wide)
    
    <div>
    

    > [!IMPORTANT]  
    > La normalizzazione eseguita dal servizio Rubrica (ABS) non sostituisce o Elimina in altro modo la necessità di normalizzare il numero di telefono principale di ogni utente in servizi di dominio Active Directory, perché ABS non ha accesso a servizi di dominio Active Directory e quindi non può copiare i numeri primari nell'attributo <STRONG>msRTCSIP-line</STRONG> .

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>Passaggio 2. Abilitare gli utenti per VoIP aziendale

Oltre a identificare gli utenti che devono essere abilitati, non è necessaria alcuna pianificazione speciale per completare questo passaggio.

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>Passaggio 3. Preparare i dial plan per gli utenti.

Gli utenti abilitati per VoIP aziendale non saranno in grado di effettuare chiamate alla rete PSTN senza dial plan in posizione. Un dial plan è un set denominato di regole di normalizzazione che converte i numeri di telefono per una posizione denominata, un singolo utente o un oggetto contatto in un unico formato standard (E. 164) per scopi di autorizzazione del telefono e routing delle chiamate. Le regole di normalizzazione definiscono il modo in cui i numeri di telefono espressi in diversi formati devono essere instradati per ogni posizione, utente o oggetto contatto specificato.

Per informazioni sulla preparazione di dial plan, vedere [dial plan e regole di normalizzazione in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>Passaggio 4. Pianificare i criteri vocali degli utenti

Le impostazioni di classe del servizio utente in un PBX legacy, ad esempio il diritto di effettuare chiamate interurbane o internazionali da telefoni aziendali, devono essere riconfigurate come criteri VoIP per gli utenti spostati in Enterprise Voice. Per informazioni dettagliate sulla pianificazione e la creazione di criteri per VoIP aziendale, vedere [criteri vocali in Lync Server 2013](lync-server-2013-voice-policies.md).

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>Passaggio 5. Pianificare le route delle chiamate in uscita

Le route di chiamata specificano il modo in cui Lync Server gestisce le chiamate in uscita poste dagli utenti VoIP aziendale. Quando un utente compone un numero, il server, se necessario, normalizza la stringa di chiamata in formato e. 164 e tenta di associarla a un URI SIP. Se il server non è in grado di eseguire la corrispondenza, applica la logica di routing delle chiamate in uscita in base al numero. Il passaggio finale per definire la logica consiste nel creare una route di chiamata separata denominata per ogni set di numeri di telefono di destinazione elencati in ogni dial plan.

Per informazioni dettagliate sulla pianificazione delle route di chiamata, vedere [route vocali in Lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>Passaggio 6. Configurare PBX o trunk SIP per reindirizzare le chiamate per gli utenti di VoIP aziendale

Gli utenti che in precedenza erano ospitati in un PBX tradizionale o in una connessione trunk SIP a un provider di servizi di telefonia Internet (ITSP) mantengono i numeri di telefono dopo lo stato di trasferimento. L'unico requisito è che dopo lo stato di trasferimento il PBX o il trunk SIP debba essere riconfigurato per instradare le chiamate in arrivo per gli utenti di VoIP aziendale al Mediation Server.

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>Passaggio 7. Trasferire gli utenti alla messaggistica unificata di Exchange (scelta consigliata)

Lo spostamento degli utenti alla messaggistica unificata di Exchange è costituito dalle attività seguenti:

  - Configurare la messaggistica unificata di Exchange e il server Lync per collaborare.

  - Consentire agli utenti di rispondere alle chiamate di messaggistica unificata di Exchange e Outlook Voice Access. Questa attività viene eseguita nel server Messaggistica unificata di Exchange. Per informazioni dettagliate, vedere la raccolta TechNet di [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)Exchange Server 2010.

</div>

</div>

<span> </span>

</div>

</div>

</div>

