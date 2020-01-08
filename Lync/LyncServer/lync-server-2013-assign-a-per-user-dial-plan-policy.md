---
title: 'Lync Server 2013: assegnare un criterio per il dial plan per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f9bca09515daba6db7e072625d5b4a217d37cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979656"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>Assegnare un criterio di dial plan per utente in Lync Server 2013

 


Per completare la configurazione dell'account utente per gli utenti di VoIP aziendale o per gli utenti di servizi di conferenza telefonica con accesso esterno, l'utente deve essere assegnato a un dial plan. Gli account utente utilizzeranno automaticamente il dial plan globale o, se disponibile, il dial plan a livello di sito quando non si assegna esplicitamente un dial plan per utente esistente. Se si vuole usare il dial plan globale o del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione.

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>Per assegnare un dial plan tramite il pannello di controllo di Lync Server 2013

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **utenti**.

4.  Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si vuole abilitare e quindi fare clic su **trova**.

5.  Nella tabella fare clic sull'account utente che si vuole assegnare a un dial plan.

6.  Nel menu **modifica** fare clic su **Mostra dettagli**.

7.  Nella pagina **modifica utente di Lync Server** , in **telefonia**, fare clic su **VoIP aziendale**.

8.  Fare clic su **Criteri dial plan**e quindi scegliere il dial plan desiderato.

9.  Fare clic su **Commit**.

Per informazioni dettagliate sulla configurazione dei dial plan, vedere l'argomento [configurazione di dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>Assegnare un dial plan per utente usando i cmdlet di Windows PowerShell

È possibile assegnare piani di dial per utente con Windows PowerShell e il cmdlet **Grant-CsdialPlan** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Per assegnare un dial plan per utente a un singolo utente

  - Con il comando seguente viene assegnato il dial plan per utente "RedmondDialPlan" all'utente Ken.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Per assegnare un dial plan per utente a più utenti

  - Questo comando assegna il dial plan per utente "RedmondDialPlan" a tutti gli utenti che lavorano nella città di Redmond. Per altre informazioni sul parametro LdapFilter usato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>Per annullare l'assegnazione di un dial plan per utente

  - Il comando seguente annulla l'assegnazione di un dial plan per utente precedentemente assegnato a Ken. Dopo la mancata assegnazione del dial plan per utente, Ken è gestito automaticamente tramite il dial plan globale, il dial plan locale (se presente) o il dial plan di servizio assegnato al proprio registrar o al gateway PSTN. Un dial plan per l'ambito dei servizi ha la precedenza su qualsiasi piano di dial-up del sito e il dial plan di un sito ha la precedenza sul dial plan globale.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) .

## <a name="see-also"></a>Vedere anche


[Configurazione dei dial plan in Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Account utente abilitato per Lync Server 2013](lync-server-2013-user-accounts-enabled-for-lync-server.md)

