---
title: Test delle autorizzazioni di amministratore in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Come verificare le autorizzazioni di amministratore in Skype for Business Server
ms.openlocfilehash: 1bae61dd4e8d5a8636a64687d279536b4989d104
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188504"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Test delle autorizzazioni di amministratore in Skype for Business Server

| | |
|--|--|
|Pianificazione della verifica|Dopo la distribuzione iniziale di Skype for Business Server. Se necessario, se sorgono problemi relativi alle autorizzazioni.|
|Strumento di test|Windows PowerShell|
|Autorizzazioni necessarie|Quando si esegue localmente usando Skype for Business Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.<br><br/>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsOUPermission. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlet-confronta "Test-CsOUPermission"}|
|||

## <a name="description"></a>Descrizione

Quando si installa Skype for Business Server, una delle attività eseguite dal programma di installazione offre al gruppo RTCUniversalUserAdmins le autorizzazioni di Active Directory necessarie per gestire utenti, computer, contatti, contatti delle applicazioni e InetOrg persone. Se è stata disabilitata l'ereditarietà delle autorizzazioni in Active Directory, il programma di installazione non sarà in grado di assegnare tali autorizzazioni. Di conseguenza, i membri del gruppo RTCUniversalUserAdmins non saranno in grado di gestire le entità di Skype for Business Server. Tali privilegi di gestione saranno disponibili solo per gli amministratori di dominio. 

Il cmdlet Test-CsOUPermission verifica che le autorizzazioni necessarie per la gestione di utenti, computer e altri oggetti vengano impostate in un contenitore di Active Directory. Se tali autorizzazioni non sono impostate, è possibile risolvere il problema eseguendo il [cmdlet Grant-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission). 

Tieni presente che Grant-CsOUPermission può assegnare le autorizzazioni solo ai membri del gruppo RTCUniversalUserAdmins. Non è possibile usare questo cmdlet per concedere le autorizzazioni a un utente o un gruppo arbitrario. Se si vuole che un utente o un gruppo diverso disponga delle autorizzazioni di gestione degli utenti, è necessario aggiungere l'utente (o il gruppo) al gruppo RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Eseguire il test

Per verificare che le autorizzazioni di gestione siano impostate in un contenitore, eseguire il cmdlet Test-CsOUPermission seguito dal nome distinto del contenitore e dal tipo di autorizzazioni da verificare. Questo comando, ad esempio, controlla se le autorizzazioni utente sono impostate nell'ou ou = Redmond, DC = litwareinc, DC = com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Per verificare più autorizzazioni con un solo comando, racchiudere ogni tipo di autorizzazione racchiuso tra virgolette, quindi separare i tipi usando le virgole. Questo comando, ad esempio, verifica le autorizzazioni utente, computer e contatto:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Per altre informazioni, vedere l' [argomento della Guida relativo al cmdlet Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se le autorizzazioni necessarie sono già state impostate, Test-CsOUPermission restituirà una risposta di una sola parola:

True

Se le autorizzazioni necessarie non sono impostate, Test-CsOUPermission restituirà il valore false. Potrebbe essere necessario cercare un momento per trovare questo valore. Verrà in genere incorporato all'interno di diversi avvisi di accompagnamento. Ad esempio:

AVVISO: voce di controllo di accesso (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; consentire ReadProperty ContainerInherit Discendenti bf967aba-0de6-11D0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

AVVISO: le voci di controllo di accesso (ACE) nell'oggetto "OU = NorthAmerica, DC = atl-cs-001\DC = litwareinc, DC = com" non sono pronte. 

False 

AVVISO: l'elaborazione "Test-CsOUPermission" è stata completata con gli avvisi. gli avvisi "2" sono stati registrati durante l'esecuzione. 

AVVISO: i risultati dettagliati possono essere trovati in "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Se Test-CsOUPermission ha esito negativo, in genere significa che l'autorizzazione specificata non è stata assegnata al gruppo RTCUniversalUserAdmins. È possibile risolvere il problema e assegnare le autorizzazioni necessarie usando il cmdlet Grant-CsOUPermission. Ad esempio, questo comando fornisce le autorizzazioni di UO per utenti, contatti e InetOrgPerson al gruppo RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Per altre informazioni, vedere l' [argomento della Guida relativo al cmdlet Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).
