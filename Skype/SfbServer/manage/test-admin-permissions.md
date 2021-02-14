---
title: Test delle autorizzazioni di amministratore in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Come testare le autorizzazioni di amministratore in Skype for Business Server
ms.openlocfilehash: 27ae50cca0018985ad59dbc4487dd3630cb5cf87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800096"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Test delle autorizzazioni di amministratore in Skype for Business Server

| | |
|--|--|
|Pianificazione della verifica|Dopo la distribuzione iniziale di Skype for Business Server. Se necessario, in caso di problemi relativi alle autorizzazioni.|
|Strumento di test|Windows PowerShell|
|Autorizzazioni necessarie|Quando vengono eseguiti localmente tramite Skype for Business Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.<br><br/>Quando viene eseguito utilizzando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che dispone dell'autorizzazione per eseguire il cmdlet Test-CsOUPermission. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando seguente dal prompt Windows PowerShell seguente:<br/><br/>Get-CsAdminRole Where-Object \| {$_. Cmdlet -match "Test-CsOUPermission"}|
|||

## <a name="description"></a>Descrizione

Quando si installa Skype for Business Server, una delle attività eseguite dal programma di installazione assegna al gruppo RTCUniversalUserAdmins le autorizzazioni di Active Directory necessarie per gestire utenti, computer, contatti, contatti dell'applicazione e persone InetOrg. Se l'ereditarietà delle autorizzazioni è stata disabilitata in Active Directory, il programma di installazione non sarà in grado di assegnare tali autorizzazioni. Di conseguenza, i membri del gruppo RTCUniversalUserAdmins non saranno in grado di gestire le entità di Skype for Business Server. Tali privilegi di gestione saranno disponibili solo per gli amministratori di dominio. 

Il Test-CsOUPermission cmdlet verifica che le autorizzazioni necessarie per gestire utenti, computer e altri oggetti siano impostate su un contenitore di Active Directory. Se tali autorizzazioni non sono impostate, è possibile risolvere il problema eseguendo il [cmdlet Grant-CsOUPermission.](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) 

Tenere presente Grant-CsOUPermission assegnare autorizzazioni solo ai membri del gruppo RTCUniversalUserAdmins. Non è possibile utilizzare questo cmdlet per concedere autorizzazioni a un utente o a un gruppo arbitrario. Se si desidera che un utente o un gruppo diverso abbia le autorizzazioni di gestione degli utenti, è necessario aggiungere tale utente (o gruppo) al gruppo RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Esecuzione del test

Per verificare che le autorizzazioni di gestione siano impostate in un contenitore, eseguire il cmdlet Test-CsOUPermission seguito dal nome distinto del contenitore e dal tipo di autorizzazioni che si sta verificando. Ad esempio, questo comando controlla se le autorizzazioni utente sono impostate sull'unità organizzativa ou=Redmond,dc=litwareinc,dc=com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Per verificare più autorizzazioni utilizzando un singolo comando, racchiudere ogni tipo di autorizzazione racchiuso tra virgolette, quindi separare tali tipi utilizzando le virgole. Ad esempio, questo comando verifica le autorizzazioni utente, computer e contatto:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Per ulteriori informazioni, vedere [l'argomento della Guida relativo Test-CsOUPermission cmdlet.](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se le autorizzazioni necessarie sono già state impostate, Test-CsOUPermission restituirà una risposta di una sola parola:

Vero

Se le autorizzazioni necessarie non sono impostate, Test-CsOUPermission restituirà il valore False. Potrebbe essere necessario cercare un momento per trovare questo valore. In genere, viene incorporato all'interno di diversi avvisi. Ad esempio:

AVVISO: voce di controllo di accesso (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Discendenti; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

AVVISO: le voci di controllo di accesso (ACE) sull'oggetto "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" non sono pronte. 

Falso 

AVVISO: l'elaborazione "Test-CsOUPermission" è stata completata con avvisi. Durante l'esecuzione sono stati registrati avvisi "2". 

AVVISO: risultati dettagliati sono disponibili in "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Se Test-CsOUPermission ha esito negativo, in genere l'autorizzazione specificata non è stata assegnata al gruppo RTCUniversalUserAdmins. È possibile risolvere il problema e assegnare le autorizzazioni necessarie utilizzando il cmdlet Grant-CsOUPermission. Ad esempio, questo comando assegna le autorizzazioni ou per utenti, contatti e inetOrgPersons al gruppo RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Per ulteriori informazioni, vedere [l'argomento della Guida relativo Test-CsOUPermission cmdlet.](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)
