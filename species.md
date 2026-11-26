---
layout: default
title: Browse species
permalink: /species/
---

<link rel="stylesheet" href="https://cdn.datatables.net/2.1.8/css/dataTables.dataTables.min.css">

[← Back to home]({{ '/' | relative_url }})

## Browse species (v{{ site.latest_version }})

Search by any field: species, family, archipelago, status… Status codes are explained in the [data dictionary]({{ '/variables/' | relative_url }}).

<div id="loading">Loading data…</div>
<div style="overflow-x:auto">
<table id="spp" class="display compact" style="width:100%; font-size:0.85em"></table>
</div>

<script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
<script src="https://cdn.datatables.net/2.1.8/js/dataTables.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/papaparse@5.4.1/papaparse.min.js"></script>
<script>
  // Columns shown in the browser; the full set is in the CSV download.
  const show = ["species","status","order","family","archipelago","region",
                "island_endemicity","flight_ability","body_mass","wing_length",
                "tarsus_length","beak_length_culmen"];
  Papa.parse("{{ site.latest_data | relative_url }}", {
    download: true, header: true, skipEmptyLines: true,
    complete: function (res) {
      document.getElementById("loading").remove();
      new DataTable("#spp", {
        data: res.data,
        columns: show.map(c => ({
          data: c,
          title: c.replace(/_/g, " "),
          render: c === "species" ? (d => "<em>" + d.replace(/_/g, " ") + "</em>") : null
        })),
        pageLength: 25
      });
    },
    error: function () {
      document.getElementById("loading").textContent = "Could not load the data file.";
    }
  });
</script>
