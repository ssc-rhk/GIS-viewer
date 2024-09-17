<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="initial-scale=1,maximum-scale=1,user-scalable=no" />
    <title>Test viewer - Basic GIS viewer</title>

    <style>
      html,
      body,
      #viewDiv {
        padding: 0;
        margin: 0;
        height: 100%;
        width: 100%;
      }
      #featureTableDiv {
        height: 30%;
        width: 100%;
        position: absolute;
        bottom: 0;
        z-index: 99;
      }

    </style>

    <link rel="stylesheet" href="https://js.arcgis.com/4.30/esri/themes/light/main.css" />

    <script src="https://js.arcgis.com/4.30/"></script>

    <script>
      require([
        "esri/config",
        "esri/views/MapView",
        "esri/WebMap",
        "esri/widgets/Editor",
        "esri/widgets/Legend",
      ], (esriConfig, MapView, WebMap, Editor, Legend, FeatureTable, FeatureLayer, UniqueValueRenderer) => {
        esriConfig.portalUrl = "https://rhk.maps.arcgis.com/";
        esriConfig.apiKey = "AAPTxy8BH1VEsoebNVZXo8HurFqir_ZdU2-7FpzvQ2oQTUAzQyPgxihKBF-QyocDiMryLv1qL2Figsi2UWydAy9JQCu3Jfgg5ZdVVv0uTF5xwacviLsj0DdZj6lBkLGc6rZ089-ZkY6fvLe5E5NfF5K1GN2C8j2f-552VeOMlF6OBcxHBPBkPLBNjduxJnp9HSvD6tmQhHtT8ki6SYntcNQRCqRtOXrKyd-Rz2qzKFXgwzUFWI3xfBv-buDWi0lQcIvMAT1_ygmuZYkx"
        const webmap = new WebMap({
          portalItem: {
            id: "7629a69342464eff8a3a0ee5f933fbd7"
          }
        });

        const view = new MapView({
          map: webmap,
          container: "viewDiv"
        });

        const editor = new Editor({
          view: view
        });

        const legend = new Legend({
          view: view
        });

        view.ui.add(editor, "top-right");
        view.ui.add(legend, "top-left");

      });
    </script>
  </head>

  <body>
    <div id="viewDiv"></div>
  </body>
</html>
