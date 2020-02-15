---
title: Verifica delle autorizzazioni di amministratore in Skype for Business Server
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
description: Come verificare le autorizzazioni di amministratore in Skype for Business Server
ms.openlocfilehash: 1e06c87dcf0e436d72c510a2bc8d9f2aa2051620
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030159"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Verifica delle autorizzazioni di amministratore in Skype for Business Server

| | |
|--|--|
|Pianificazione della verifica|Dopo la distribuzione iniziale di Skype for Business Server. Se necessario, se si verificano problemi relativi alle autorizzazioni.|
|Strumento di testing|Windows PowerShell|
|Autorizzazioni necessarie|Quando si esegue localmente usando Skype for Business Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.<br><br/>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsOUPermission. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlet-match "Test-CsOUPermission"}|
|||

## <a name="description"></a>Descrizione

Quando si installa Skype for Business Server, una delle attività eseguite dal programma di installazione conferisce al gruppo RTCUniversalUserAdmins le autorizzazioni di Active Directory necessarie per la gestione di utenti, computer, contatti, contatti di applicazioni e InetOrg persone. Se è stata disabilitata l'ereditarietà delle autorizzazioni in Active Directory, il programma di installazione non sarà in grado di assegnare tali autorizzazioni. Di conseguenza, i membri del gruppo RTCUniversalUserAdmins non saranno in grado di gestire le entità di Skype for Business Server. Tali privilegi di gestione saranno disponibili solo per gli amministratori di dominio. 

Il cmdlet Test-CsOUPermission verifica che le autorizzazioni necessarie per la gestione degli utenti, dei computer e di altri oggetti siano impostate su un contenitore di Active Directory. Se tali autorizzazioni non sono impostate, è possibile risolvere il problema eseguendo il [cmdlet Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission). 

Si noti che Grant-CsOUPermission può assegnare solo le autorizzazioni ai membri del gruppo RTCUniversalUserAdmins. Non è possibile utilizzare questo cmdlet per concedere le autorizzazioni a un utente o un gruppo arbitrario. Se si desidera che un utente o un gruppo diverso disponga delle autorizzazioni per la gestione degli utenti, è necessario aggiungere tale utente (o gruppo) al gruppo RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Esecuzione del test

Per verificare che le autorizzazioni di gestione siano impostate su un contenitore, eseguire il cmdlet Test-CsOUPermission seguito dal nome distinto del contenitore e dal tipo di autorizzazioni che si sta verificando. Ad esempio, questo comando consente di controllare se le autorizzazioni utente sono impostate nell'unità organizzativa OU = Redmond, DC = litwareinc, DC = com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Per verificare più autorizzazioni utilizzando un singolo comando, racchiudere ogni tipo di autorizzazione racchiuso tra virgolette, quindi separare i tipi utilizzando le virgole. Ad esempio, questo comando consente di verificare le autorizzazioni utente, computer e contatti:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Per ulteriori informazioni, vedere l' [argomento della Guida relativo al cmdlet Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se le autorizzazioni necessarie sono già state impostate, Test-CsOUPermission restituirà una risposta a una sola parola:

True

Se le autorizzazioni necessarie non sono impostate, Test-CsOUPermission restituirà il valore false. Potrebbe essere necessario cercare un momento per trovare questo valore. In genere viene incorporato all'interno di diversi avvisi di accompagnamento. Ad esempio:

AVVISO: voce di controllo di accesso (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; consentire ReadProperty ContainerInherit Discendenti bf967aba-0de6-11D0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

AVVISO: le voci di controllo di accesso (ACE) dell'oggetto "OU = NorthAmerica, DC = atl-cs-001\DC = litwareinc, DC = com" non sono pronte. 

False 

AVVISO: l'elaborazione di "Test-CsOUPermission" è stata completata con gli avvisi. gli avvisi "2" sono stati registrati durante la fase di esecuzione. 

AVVISO: i risultati dettagliati sono disponibili su "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Se Test-CsOUPermission ha esito negativo, in genere significa che l'autorizzazione specificata non è stata assegnata al gruppo RTCUniversalUserAdmins. È possibile risolvere il problema e assegnare le autorizzazioni necessarie utilizzando il cmdlet Grant-CsOUPermission. Ad esempio, questo comando fornisce le autorizzazioni di unità organizzativa per utenti, contatti e InetOrgPerson al gruppo RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Per ulteriori informazioni, vedere l' [argomento della Guida relativo al cmdlet Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).
