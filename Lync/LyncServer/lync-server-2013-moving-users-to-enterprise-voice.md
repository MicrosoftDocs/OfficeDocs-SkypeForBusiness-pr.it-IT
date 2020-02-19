---
title: 'Lync Server 2013: spostamento di utenti in VoIP aziendale'
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
ms.openlocfilehash: 968e70e74cd129f05d4f39f626d9e21b1c3dc33a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>Spostamento di utenti in VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-18_

Se si sta spostando gli utenti da un'infrastruttura di telefonia PBX esistente a VoIP aziendale, il processo di distribuzione include alcuni passaggi che non fanno parte del processo di pianificazione già descritto in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md). Per informazioni sulla migrazione di utenti da una distribuzione di VoIP aziendale precedente, vedere i documenti sulla migrazione inclusi con il supporto di installazione.

Il processo di trasferimento degli utenti da un'infrastruttura di telefonia esistente a VoIP aziendale è costituito dai seguenti passaggi:

1.  Designazione dei numeri di telefono primari.

2.  Abilitazione degli utenti per VoIP aziendale.

3.  Preparazione dei dial plan per gli utenti.

4.  Pianificazione dei criteri vocali per gli utenti.

5.  Pianificazione delle route delle chiamate.

6.  Configurazione del sistema PBX o del trunk SIP per il reinstradamento delle chiamate degli utenti abilitati per VoIP aziendale.

7.  Spostare gli utenti nella messaggistica unificata di Exchange (scelta consigliata).

In questo argomento sono descritte le attività di pianificazione necessarie per ognuno di questi passaggi.

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>Passaggio 1. Designare i numeri di telefono primari

VoIP aziendale integra funzionalità vocali con altre funzionalità multimediali di messaggistica. Ad esempio, quando il server riceve una chiamata in arrivo, esegue il mapping del numero all'URI SIP dell'utente e quindi inoltra la chiamata a tutti gli endpoint client associati a tale URI SIP. Per questo processo è necessario che ogni utente sia associato a un numero di telefono primario.

Un numero di telefono primario deve avere le caratteristiche seguenti:

  - Deve essere globalmente univoco o, nel caso dei numeri di interno, univoco nell'azienda.

  - Deve essere di proprietà dell'azienda e instradabile. Non deve essere un numero personale.

Per gli utenti dell'organizzazione possono essere presenti due o più numeri di telefono in servizi di dominio Active Directory. Tutti i numeri di telefono associati a un determinato utente possono essere visualizzati o modificati nella finestra delle proprietà dello snap-in Utenti e computer di Active Directory.

La casella **Numero di telefono** nella scheda **Generale** della finestra di dialogo **Proprietà utente** deve contenere il numero di lavoro principale dell'utente. Questo numero viene in genere designato come numero di telefono primario.

Alcuni utenti potrebbero avere requisiti particolari, ad esempio per un dirigente può essere necessario instradare tutte le chiamate in arrivo a un assistente amministrativo. Tali eccezioni devono essere limitate solo a casi di evidente necessità.

Una volta scelto, il numero primario deve essere:

  - Normalizzato nel formato E.164, quando possibile.

  - Copiato nell'attributo **msRTCSIP-line** di Active Directory.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>Coesistenza con il controllo delle chiamate remote (RCC)</STRONG><BR>RCC è la possibilità di utilizzare Lync Server per monitorare e controllare un telefono PBX desktop. Il controllo viene instradato attraverso il server, che funge da gateway per il sistema PBX. Anche se non è possibile configurare un utente per le chiamate remote e VoIP aziendale, l'impostazione URI linea designa il numero di telefono principale di un utente in entrambi i casi.<BR>Se si desidera continuare a utilizzare l'infrastruttura PBX esistente per alcuni utenti selezionati, è possibile introdurre VoIP aziendale nell'organizzazione in modo graduale. Per informazioni dettagliate su questo scenario di distribuzione, vedere <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP Deployment Options in Lync Server 2013</A> nella documentazione relativa alla pianificazione.<BR>Nelle versioni precedenti, è possibile abilitare sia RCC che VoIP aziendale per un utente, ma solo se è stato configurato anche l'utente per il dual forking, una funzionalità in cui una chiamata in arrivo suonerà contemporaneamente il telefono PBX e Communicator di un utente. In Lync Server 2010, il dual-forking non è supportato.

    
    </div>

Per popolare l'attributo **msRTCSIP-line** sono disponibili tre metodi:

  - Microsoft Identity Integration Server (scelta consigliata)

  - La pagina **utenti** nel pannello di controllo di Lync Server

Dove devono essere elaborati molti numeri di telefono, uno script personalizzato sviluppato dall'organizzazione è la scelta migliore. A seconda della modalità con cui l'organizzazione rappresenta i numeri di telefono in Servizi di dominio Active Directory, può essere necessario utilizzare lo script per normalizzare i numeri di telefono primari in base al formato E.164 prima di copiarli nell'attributo **msRTCSIP-line**.

  - Se l'organizzazione gestisce tutti i numeri di telefono in un unico formato in Servizi di dominio Active Directory e se tale formato è E.164, è necessario utilizzare lo script solo per scrivere ogni numero di telefono primario nell'attributo **msRTCSIP-line**.

  - Se l'organizzazione gestisce tutti i numeri di telefono in un unico formato in Servizi di dominio Active Directory, ma tale formato non è E.164, è necessario utilizzare lo script per definire una regola di normalizzazione appropriata in modo da convertire i numeri di telefono primari dal formato esistente in E.164 prima di scriverli nell'attributo **msRTCSIP-line**.

  - Se l'organizzazione non adotta un formato standard per i numeri di telefono in Servizi di dominio Active Directory, è necessario utilizzare lo script per definire le regole di normalizzazione appropriate per convertire i numeri di telefono primari dai diversi formati in un formato conforme a E.164 prima di scriverli nell'attributo **msRTCSIP-line**.

Lo script dovrà inoltre aggiungere il prefisso **Tel:** ai numeri primari prima di scriverli nell'attributo**msRTCSIP-line**.

Il formato previsto del numero specificato in questo attributo è il seguente:

  - Tel: + 14255550100; ext = 50100.

  - Tel:5550100 (per i numeri di interno univoci a livello aziendale)
    
    <div>
    

    > [!IMPORTANT]  
    > La normalizzazione eseguita dal servizio Rubrica (ABS) non sostituisce né elimina in altro modo la necessità di normalizzare il numero di telefono primario di ogni utente in Servizi di dominio Active Directory. ABS infatti non dispone dell'accesso a Servizi di dominio Active Directory e pertanto non può copiare i numeri primari nell'attributo <STRONG>msRTCSIP-line</STRONG>.

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>Passaggio 2. Abilitare gli utenti per VoIP aziendale

Oltre a identificare gli utenti da abilitare, per completare questo passaggio non sono necessarie attività di pianificazione particolari.

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>Passaggio 3. Preparare i dial plan per gli utenti.

Senza un dial plan gli utenti abilitati per VoIP aziendale non sono in grado di effettuare chiamate a PSTN. Per dial plan si intende un set denominato di regole di normalizzazione che consente di convertire i numeri di telefono relativi a una località, a un utente o a un oggetto contatto specifico in un unico formato standard (E.164) ai fini dell'autorizzazione del telefono e del routing della chiamata. Le regole di normalizzazione definiscono la modalità di instradamento dei numeri di telefono espressi in diversi formati per ogni località, utente o oggetto contatto.

Per informazioni sulla preparazione dei dial plan, vedere [dial plan e regole di normalizzazione in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>Passaggio 4. Pianificare i criteri vocali degli utenti

Le impostazioni utente relative alla classe di servizio in un sistema PBX legacy, ad esempio il diritto di effettuare chiamate interurbane o internazionali dai telefoni dell'azienda, devono essere configurate come criteri VoIP per gli utenti trasferiti in VoIP aziendale. Per informazioni dettagliate sulla pianificazione e la creazione di criteri per VoIP aziendale, vedere [criteri vocali in Lync Server 2013](lync-server-2013-voice-policies.md).

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>Passaggio 5. Pianificare le route delle chiamate in uscita

Route di chiamata specificare in che modo Lync Server gestisce le chiamate in uscita effettuate dagli utenti di VoIP aziendale. Quando un utente compone un numero, il server, se necessario, normalizza la stringa di composizione nel formato E.164 e tenta di associarla a un URI SIP. Se per il server non è possibile effettuare l'associazione, verrà applicata la logica di routing delle chiamate in uscita in base al numero. Il passaggio finale della definizione della logica consiste nel creare una route di chiamate denominate separate per ogni insieme di numeri di telefono di destinazione elencati in ogni dial plan.

Per informazioni dettagliate sulla pianificazione delle route di chiamata, vedere [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>Passaggio 6. Configurare il sistema PBX o il trunk SIP per il reinstradamento delle chiamate degli utenti abilitati per VoIP aziendale

Dopo il trasferimento, gli utenti precedentemente ospitati in un'infrastruttura PBX tradizionale o che usufruivano di una connessione trunk SIP Trunk a un provider di telefonia Internet (ITSP, Internet Telephony Service Provider) mantengono lo stesso numero di telefono. L'unico requisito è che dopo lo spostamento, il PBX o il trunk SIP deve essere riconfigurato per instradare le chiamate in arrivo per gli utenti di VoIP aziendale al Mediation Server.

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>Passaggio 7. Trasferire gli utenti al servizio Messaggistica unificata di Exchange (operazione consigliata).

Il passaggio degli utenti al servizio Messaggistica unificata di Exchange è costituito dalle seguenti attività:

  - Configurazione della messaggistica unificata di Exchange e di Lync Server per la collaborazione.

  - Abilitazione degli utenti per il risponditore automatico del servizio Messaggistica unificata di Exchange e per Outlook Voice Access. Questa attività viene eseguita nel server di Messaggistica unificata di Exchange. Per informazioni dettagliate, vedere la libreria TechNet di Exchange Server [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372)2010 all'indirizzo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

