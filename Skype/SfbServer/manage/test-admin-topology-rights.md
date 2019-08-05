---
title: Test dei diritti di topologia di amministratore in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Come verificare i diritti di topologia in Skype for Business Server
ms.openlocfilehash: d70809ba929c4f1934adce2bd3c60b261bd30d71
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188501"
---
# <a name="testing-admin-topology-rights-in-skype-for-business-server"></a>Test dei diritti di topologia di amministratore in Skype for Business Server

| | |
|--|--|
|Pianificazione della verifica|Dopo la distribuzione iniziale di Skype for Business Server. Se necessario, se sorgono problemi relativi alle autorizzazioni.|
|Strumento di test|Windows PowerShell|
|Autorizzazioni necessarie|Quando si esegue localmente usando Skype for Business Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.<br/><br/>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsSetupPermission. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:<br/><br/>Get-CsAdminRole \| Where-Object {$ _. Cmdlet-confronta "Test-CsSetupPermission"}|
|||

## <a name="description"></a>Descrizione

Per impostazione predefinita, solo gli amministratori di dominio possono abilitare una topologia di Skype for Business Server e apportare grandi modifiche all'infrastruttura di Skype for Business Server. Non si tratta di un problema purché gli amministratori di dominio e gli amministratori di Skype for Business Server siano uno e lo stesso. In molte organizzazioni gli amministratori di Skype for Business Server non detieneno diritti amministrativi per l'intero dominio. Per impostazione predefinita, questo significa che questi amministratori (definiti come membri del gruppo RTCUniversalServerAdmins) non possono apportare modifiche alla topologia di Skype for Business Server. Per concedere ai membri del gruppo RTCUniversalServerAdmins il diritto di apportare modifiche alla topologia, è necessario assegnare le autorizzazioni di Active Directory necessarie usando il cmdlet [Grant-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsSetupPermission) .
 
Il cmdlet Test-CsSetupPermission verifica che le autorizzazioni necessarie per installare Skype for Business Server o uno dei relativi componenti siano configurate nel contenitore di Active Directory specificato. Se le autorizzazioni non sono assegnate, è possibile eseguire il cmdlet Grant-CsSetupPermission per assegnare ai membri del gruppo RTCUniversalServerAdmins il diritto di installare e abilitare Skype for Business Server.

## <a name="running-the-test"></a>Eseguire il test

Per determinare se le autorizzazioni di configurazione sono assegnate per un contenitore di Active Directory, chiama il cmdlet Test-CsSetupPermission. Specificare il nome distinto del contenitore da controllare. Questo comando, ad esempio, verifica le autorizzazioni di configurazione per il contenitore ou = CsServers, DC = litwareinc, DC = com:

`Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"`

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Se Test-CsSetupPermission determina che le autorizzazioni necessarie sono già state impostate in un contenitore di Active Directory, il cmdlet restituirà il valore true:

True 

Se le autorizzazioni non sono impostate, Test-CsSetupPermission restituirà il valore false. Tieni presente che questo valore verrà in genere racchiuso in molti messaggi di avviso. Ad esempio:

AVVISO: voce di controllo di accesso (ACE) atl-cs-001\RTCUniversalServerAdmins; Consentire ExtendedRight; Nessuno Nessuno 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2 

AVVISO: le voci di controllo di accesso (ACE) nell'oggetto "CN = Computers, DC = litwareinc, DC = com" non sono pronte. 

False 

AVVISO: l'elaborazione "Test-CsSetupPermission" è stata completata con gli avvisi. gli avvisi "2" sono stati registrati durante l'esecuzione. 

AVVISO: i risultati dettagliati possono essere trovati in "C:\Users\Admin\AppData\Local\Temp\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html". 

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Anche se esistono eccezioni rare, se Test-CsSetupPermission non riesce in genere significa che le autorizzazioni di configurazione non vengono assegnate per il contenitore di Active Directory specificato. Queste autorizzazioni possono essere assegnate usando il cmdlet Grant-CsSetupPermission. Questo comando, ad esempio, concede le autorizzazioni di configurazione al contenitore di computer nel dominio litwareinc.com:

`Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"`

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsSetupPermission) .
