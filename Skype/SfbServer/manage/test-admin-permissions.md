---
title: Test delle autorizzazioni di amministratore in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Come testare le autorizzazioni di amministratore in Skype for Business Server
ms.openlocfilehash: 80971dab292252775f9a58cbf822d746326c8abf
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760694"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a>Test delle autorizzazioni di amministratore in Skype for Business Server

|&nbsp; |&nbsp; |
|--|--|
|Pianificazione della verifica|Dopo la distribuzione Skype for Business Server iniziale. Se necessario, se si verificano problemi relativi alle autorizzazioni.|
|Strumento di testing|Windows PowerShell|
|Autorizzazioni necessarie|Quando vengono eseguiti localmente Skype for Business Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.<br><br/>Quando viene eseguito utilizzando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che dispone dell'autorizzazione per eseguire il cmdlet Test-CsOUPermission. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando seguente dal prompt Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$_. Cmdlet -match "Test-CsOUPermission"}|
|||

## <a name="description"></a>Descrizione

Quando si installa Skype for Business Server, una delle attività eseguite dal programma di installazione assegna al gruppo RTCUniversalUserAdmins le autorizzazioni di Active Directory necessarie per gestire utenti, computer, contatti, contatti dell'applicazione e persone InetOrg. Se è stata disabilitata l'ereditarietà delle autorizzazioni in Active Directory, il programma di installazione non sarà in grado di assegnare tali autorizzazioni. Di conseguenza, i membri del gruppo RTCUniversalUserAdmins non saranno in grado di gestire Skype for Business Server entità. Tali privilegi di gestione saranno disponibili solo per gli amministratori di dominio. 

Il cmdlet Test-CsOUPermission verifica che le autorizzazioni necessarie per gestire utenti, computer e altri oggetti siano impostate su un contenitore di Active Directory. Se tali autorizzazioni non sono impostate, è possibile risolvere il problema eseguendo il [cmdlet Grant-CsOUPermission](/powershell/module/skype/Grant-CsOUPermission). 

Tenere presente Grant-CsOUPermission possono assegnare autorizzazioni solo ai membri del gruppo RTCUniversalUserAdmins. Non è possibile utilizzare questo cmdlet per concedere autorizzazioni a un utente o a un gruppo arbitrario. Se si desidera che un utente o un gruppo diverso abbia autorizzazioni di gestione degli utenti, è necessario aggiungere tale utente (o gruppo) al gruppo RTCUniversalUserAdmins. 


## <a name="running-the-test"></a>Esecuzione del test

Per verificare che le autorizzazioni di gestione siano impostate in un contenitore, eseguire il cmdlet Test-CsOUPermission seguito dal nome distinto del contenitore e dal tipo di autorizzazioni da verificare. Ad esempio, questo comando controlla se le autorizzazioni utente sono impostate nell'unità organizzativa ou=Redmond,dc=litwareinc,dc=com:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

Per verificare più autorizzazioni utilizzando un singolo comando, racchiudere ogni tipo di autorizzazione racchiuso tra virgolette, quindi separare tali tipi utilizzando le virgole. Ad esempio, questo comando verifica le autorizzazioni utente, computer e contatto:

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

Per ulteriori informazioni, vedere l'argomento della Guida [relativo al cmdlet Test-CsOUPermission .](/powershell/module/skype/test-csoupermission)

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Se le autorizzazioni necessarie sono già state impostate, Test-CsOUPermission restituirà una risposta di una sola parola:

Vero

Se le autorizzazioni necessarie non sono impostate, Test-CsOUPermission restituirà il valore False. Potrebbe essere necessario cercare un momento per trovare questo valore. In genere verrà incorporato all'interno di diversi avvisi di accompagnamento. Ad esempio:

AVVISO: voce di controllo di accesso (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Discendenti; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4 

AVVISO: le voci di controllo di accesso (ACE) sull'oggetto "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" non sono pronte. 

Falso 

AVVISO: l'elaborazione "Test-CsOUPermission" è stata completata con avvisi. Durante questa esecuzione sono stati registrati avvisi di tipo "2". 

AVVISO: i risultati dettagliati sono disponibili in "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Se Test-CsOUPermission ha esito negativo, in genere significa che l'autorizzazione specificata non è stata assegnata al gruppo RTCUniversalUserAdmins. È possibile risolvere il problema e assegnare le autorizzazioni necessarie utilizzando il cmdlet Grant-CsOUPermission. Ad esempio, questo comando assegna le autorizzazioni dell'unità organizzativa per utenti, contatti e inetOrgPersons al gruppo RTCUniversalUserAdmins:

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

Per ulteriori informazioni, vedere l'argomento della Guida [relativo al cmdlet Test-CsOUPermission .](/powershell/module/skype/test-csoupermission)