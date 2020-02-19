---
title: 'Lync Server 2013: assegnare un criterio di dial plan per utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bd4d46e2cd41c972258a84a1e8fb34549dc8b4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134442"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a>Assegnare un criterio di dial plan per utente in Lync Server 2013

 


Per completare la configurazione degli account per gli utenti di VoIP aziendale o per gli utenti delle conferenze telefoniche con accesso esterno, è necessario che all'utente sia assegnato un dial plan. Quando non si assegna esplicitamente un dial plan per utente esistente, gli account utente utilizzeranno automaticamente il dial plan globale oppure il dial plan a livello di sito, se disponibile. Se si desidera utilizzare il dial plan globale o il dial plan del sito per tutti gli utenti abilitati per VoIP aziendale, è possibile ignorare questa sezione.

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a>Per assegnare un dial plan tramite il pannello di controllo di Lync Server 2013

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti**.

4.  Nella casella **Cerca utenti** digitare tutto o solo la prima parte del nome visualizzato, del nome, del cognome, del nome dell'account SAM (Security Accounts Manager), dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) di linea dell'account utente che si desidera abilitare e quindi fare clic su **Trova**.

5.  Nella tabella fare clic sull'account utente a cui si desidera assegnare un dial plan.

6.  Scegliere **Mostra dettagli** dal menu **Modifica**.

7.  Nella pagina **Modifica utente di Lync Server**, in **Telefonia**, fare clic su **VoIP aziendale**.

8.  Fare clic su **Criteri dial plan** e quindi scegliere il dial plan desiderato.

9.  Fare clic su **Commit**.

Per informazioni dettagliate sulla configurazione dei dial plan, vedere l'argomento [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) .

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a>Assegnare un dial plan per utente utilizzando i cmdlet di Windows PowerShell

È possibile assegnare dial plan per utente con Windows PowerShell e il cmdlet **Grant-CsdialPlan** . È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Per assegnare un dial plan per utente a un singolo utente

  - Il comando seguente assegna il dial plan per utente RedmondDialPlan all'utente Ken Myer:
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Per assegnare un dial plan per utente a più utenti

  - Questo comando assegna il dial plan per utente RedmondDialPlan a tutti gli utenti che lavorano nella città di Redmond. Per ulteriori informazioni sul parametro LdapFilter utilizzato in questo comando, vedere la documentazione relativa al cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a>Per annullare l'assegnazione di un dial plan per utente

  - Il comando seguente annulla l'assegnazione di qualsiasi dial plan per utente precedentemente assegnato a Ken Myer. Dopo l'annullamento dell'assegnazione del dial plan per utente, Ken Myer verrà gestito automaticamente mediante il dial plan globale, il dial plan del sito locale (se esistente) o il dial plan dell'ambito del servizio assegnato alla funzione di registrazione o al gateway PSTN. Un dial plan dell'ambito del servizio ha la precedenza su qualsiasi dial plan del sito, mentre un dial plan del sito ha la precedenza sul dial plan globale.
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\)) .

## <a name="see-also"></a>Vedere anche


[Configurazione di dial plan in Lync Server 2013](lync-server-2013-configuring-dial-plans.md)  
[Account utente abilitati per Lync Server 2013](lync-server-2013-user-accounts-enabled-for-lync-server.md)

