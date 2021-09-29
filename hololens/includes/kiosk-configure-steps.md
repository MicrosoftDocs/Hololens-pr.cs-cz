---
ms.openlocfilehash: 3d6b36124cd50dcc9f420227cb7787f0d787c013
ms.sourcegitcommit: c73cdefbdb4411f6a187cc38bb2570dadeb156bf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/28/2021
ms.locfileid: "129220636"
---
# <a name="microsoft-intune-single-app-kiosk-template"></a>[Microsoft Intune veřejného terminálu s jednou aplikací](#tab/uisak)

### <a name="microsoft-intune-single-app-kiosk-template"></a>Microsoft Intune veřejného terminálu s jednou aplikací

1. Vytvoření konfiguračního profilu <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Volba šablony veřejného terminálu <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Zvolte, jestli se jedná o jednu nebo více bezobrazovkové aplikace, a také zvolte druh cílení na uživatele pro bezobrazovový režim. <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-sa-3.png"/>
</kbd>

<br>

4. Volba aplikace, která se má spustit v bezobrazovkovém režimu <br>
<kbd>
    <img alt="Choose the app" src="../images/kiosk-steps/kiosk-template-sa-4.png"/>
</kbd>

<br>

5. Zbývající možnosti ponechte tak, jak jsou. <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Vyberte, ke kterým skupinám nebo zařízením nebo uživatelům se má tento konfigurační profil přiřadit. <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

7. Zkontrolujte a vytvořte konfigurační profil a uložte ho.
8. Proveďte synchronizaci MDM počínaje zařízením nebo Intune, abyste na zařízení aplikují konfiguraci. [Synchronizace zařízení z Intune](/mem/intune/remote-actions/device-sync#sync-a-device) nebo na zařízení prostřednictvím **účtů Nastavení -> -> Pracovní** nebo školní ->vyberte připojený účet **-> -> Sync**
9. Přihlaste se jako cílový uživatel a vyzkoušejte si bezobrazovkové prostředí.

# <a name="microsoft-intune-multi-app-kiosk-template"></a>[Microsoft Intune veřejného terminálu s více aplikacemi](#tab/uimak)

### <a name="microsoft-intune-multi-app-kiosk-template"></a>Microsoft Intune veřejného terminálu s více aplikacemi

1. Vytvoření konfiguračního profilu <br>
<kbd>
    <img alt="Create a configuration profile" src="../images/kiosk-steps/kiosk-template-sa-1.png"/>
</kbd>

<br>

2. Volba šablony veřejného terminálu <br>
<kbd>
    <img alt="Create a kiosk profile" src="../images/kiosk-steps/kiosk-template-sa-2.png" width="415" height="530" />
</kbd>

<br>

3. Zvolte, jestli se jedná o jednu nebo více bezobrazovkové aplikace, a také zvolte druh cílení na uživatele pro bezobrazovový režim. <br>
<kbd>
    <img alt="Select single app kiosk mode" src="../images/kiosk-steps/kiosk-template-mak-3.png"/>
</kbd>

<br>

4. Zvolte aplikace, které se spustí v bezobrazovkovém režimu. <br>
<kbd>
    <img alt="Choose the app(s)" src="../images/kiosk-steps/kiosk-template-mak-4.png"/>
</kbd>

<br>

5. Zbývající možnosti ponechte tak, jak jsou. <br>
<kbd>
    <img alt="Leave options" src="../images/kiosk-steps/kiosk-template-sa-5.png"/>
</kbd>

<br>

6. Vyberte, ke kterým skupinám nebo zařízením nebo uživatelům se má tento konfigurační profil přiřadit. <br> 
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-template-sa-6.png"/>
</kbd>

<br>

7. Zkontrolujte a vytvořte konfigurační profil a uložte ho.
8. Proveďte synchronizaci MDM počínaje zařízením nebo Intune, abyste na zařízení aplikují konfiguraci. [Synchronizace zařízení z Intune](/mem/intune/remote-actions/device-sync#sync-a-device) nebo na zařízení prostřednictvím **účtů Nastavení -> -> Pracovní** nebo školní ->vyberte připojený účet **-> -> Sync**
9. Přihlaste se jako cílový uživatel a vyzkoušejte si bezobrazovkové prostředí.

# <a name="microsoft-intune-custom-template"></a>[Microsoft Intune vlastní šablony](#tab/intunecustom)

### <a name="microsoft-intune-custom-template"></a>Microsoft Intune vlastní šablony

1. Vytvořte konfiguraci XML pro požadované prostředí veřejného terminálu. Začněte [příklady,](../hololens-kiosk-reference.md#kiosk-xml-code-samples) které najdete tady.

1. Vytvoření vlastního konfiguračního profilu <br>
<kbd>
    <img alt="Create a custom configuration profile" src="../images/kiosk-steps/kiosk-custom-1.png"/>
</kbd>

<br>

3. Zadejte název vlastního konfiguračního profilu a kliknutím na Přidat v části Nastavení konfigurace přidejte nastavení OMA-URI. <br>
<kbd>
    <img alt="Name and add" src="../images/kiosk-steps/kiosk-custom-2.png"/>
</kbd>

<br>

4. Zadejte název nastavení OMA-URI.

    1. Do textového pole OMA-URI zadejte **./Device/Vendor/MSFT/AssignedAccess/Configuration.**
    1. Jako Datový typ zvolte **Řetězec.**
    1. Do textového pole hodnota zkopírujte a vložte soubor XML konfigurace přiřazeného přístupu (příklady na základě scénáře najdete v referenčních odkazech a před vložením kopírování podle potřeby aktualizujte).
    1. Výběrem tlačítka Uložit uložte nastavení a konfiguraci.

    <kbd>
        <img alt="Specify OMA-URI settings" src="../images/kiosk-steps/kiosk-custom-3.png"/>
    </kbd>

<br>

5. Vyberte, ke kterým skupinám nebo zařízením nebo uživatelům se má tento konfigurační profil přiřadit. <br>
<kbd>
    <img alt="Choose how to assign" src="../images/kiosk-steps/kiosk-custom-4.png"/>
</kbd>

<br>

6. Zkontrolujte a vytvořte a uložte konfigurační profil.
1. Proveďte synchronizaci MDM počínaje zařízením nebo Intune, abyste na zařízení aplikují konfiguraci. [Synchronizace zařízení z Intune](/mem/intune/remote-actions/device-sync#sync-a-device) nebo na zařízení prostřednictvím **účtů Nastavení -> -> Pracovní** nebo školní ->vyberte připojený účet **-> -> Sync**
1. Přihlaste se jako cílový uživatel a vyzkoušejte si bezobrazovkové prostředí.

# <a name="runtime-provisioning---multi-app"></a>[Zřizování za běhu – Více aplikací](#tab/ppkgmak)

### <a name="runtime-provisioning---multi-app"></a>Zřizování za běhu – Více aplikací

1. Vytvořte konfiguraci XML pro požadované prostředí veřejného terminálu. Začněte [příklady,](../hololens-kiosk-reference.md#kiosk-xml-code-samples) které najdete tady.

1. Otevřete [Windows Configuration Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)

1. Na úvodní stránce vyberte **Zřídit HoloLens zařízení.** <br>
<kbd>
    <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
</kbd>

<br>

4. Vyberte **Zřídit HoloLens 2 zařízení** a pak vyberte Další. <br>
<kbd>
    <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
</kbd>

<br>

5. Pojmete svůj projekt. Volitelně můžete napsat popis. Pokračujte **výběrem** možnosti Dokončit.

6. V levém dolním rohu obrazovky vyberte **Přepnout na rozšířený editor.** Potvrďte přepnutí do rozšířeného editoru tak, že vyberete **Ano.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

7. Na levé straně rozbalte Nastavení modulu runtime, AssignedAccess a vyberte **MultiAppAssignedAccess.** <br>

    <kbd>
        <img alt="select MultiAppAssignedAccess" src="../images/kiosk-steps/kiosk-provision-3.png"/>
    </kbd>

<br>

8. Vyberte tlačítko **Procházet…** otevřete Průzkumníka souborů. A vyberte nakonfigurovaný soubor XML veřejného terminálu.

9. Vyberte **Exportovat** a pak **Zřizovací balíček**.

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

10. Změňte typ vlastníka na **Správce IT.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

11. Třikrát vyberte **Další**. Pak vyberte **Build (Sestavit).**

12. Po sestavení zřizovacího balíčku otevřete složku Umístění výstupu. Soubor .ppkg je váš zřzřídit balíček. Volitelný krok: Uložte projekt.

13. Teď můžete použít zřizovací balíček. Můžete buď použít [zřizovací balíček](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) pro HoloLens během instalace, nebo použít zřizovací balíček pro [HoloLens po instalaci](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).

14. Přihlaste se jako cílový uživatel a vyzkoušejte si bezobrazovkové prostředí.

# <a name="runtime-provisioning---single-app"></a>[Zřizování za běhu – Jedna aplikace](#tab/ppkgsak)

### <a name="runtime-provisioning---single-app"></a>Zřizování za běhu – Jedna aplikace

1. Otevřete [Windows Configuration Designer.](https://www.microsoft.com/store/apps/9nblggh4tx22)

1. Na úvodní stránce vyberte **Zřídit HoloLens zařízení.** <br>

    <kbd>
        <img alt="Selecting provision HoloLens" src="../images/kiosk-steps/kiosk-provision-1.png"/>
    </kbd>

<br>

3. Vyberte **Zřídit HoloLens 2 zařízení** a pak vyberte Další. <br>

    <kbd>
        <img alt="Select HoloLens 2" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

4. Pojmete svůj projekt. Volitelně můžete napsat popis. Pokračujte **výběrem** možnosti Dokončit.

5. V levém dolním rohu obrazovky vyberte **Přepnout na rozšířený editor.** Potvrďte přepnutí do rozšířeného editoru tak, že vyberete **Ano.** <br>

    <kbd>
        <img alt="Switch to advanced editor" src="../images/kiosk-steps/kiosk-provision-2.png"/>
    </kbd>

<br>

6. Na levé straně rozbalte Runtime settings (Nastavení modulu runtime), AssignedAccess (Přiřazený přístup) a **vyberte AssignedAccessSettings (PřiřazenýpřístupNastavení).** <br>

    <kbd>
        <img alt="Navigate to assigned access settings" src="../images/kiosk-steps/kiosk-provision-sak-1.png"/>
    </kbd>

<br>

7. V textovém poli definujte svůj bezobrazovový terminál. Následující příklad například vytvoří jeden beziosk aplikace pro místní účet s názvem LocalAccount, což je aplikace nastavení.
```{"Account":"LocalAccount","AUMID":"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App"}```

8. Vyberte **Exportovat** a pak **Zřizovací balíček**. <br>

    <kbd>
        <img alt="Export package" src="../images/kiosk-steps/kiosk-provision-4.png"/>
    </kbd>

<br>

9. Změňte typ vlastníka na **Správce IT.** <br>

    <kbd>
        <img alt="Exporting as IT Admin" src="../images/kiosk-steps/kiosk-provision-5.png"/>
    </kbd>

<br>

10. Třikrát vyberte **Další**. Pak vyberte **Build (Sestavit).**

11. Po sestavení zřizovacího balíčku otevřete složku Umístění výstupu. Soubor .ppkg je váš zřzřídit balíček. Volitelný krok: Uložte projekt.

12. Teď můžete použít zřizovací balíček. Můžete buď použít [zřizovací balíček](../hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) pro HoloLens během instalace, nebo použít zřizovací balíček pro [HoloLens po instalaci](../hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).