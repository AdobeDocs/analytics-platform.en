---
git-repo: https://github.com/adobedocs/analytics-platform.en
cloud: Experience Cloud
product: adobe analytics
sub-product: customer journey
solution: Customer Journey Analytics
type: Documentation
index: yes
user-guide-title: Customer Journey Analytics Guide
user-guide-description: Learn about Adobe Customer Journey Analytics and how to use Analysis Workspace with data from Experience Platform.
breadcrumb-title: Customer Journey Analytics Guide
---
# Adobe Customer Journey Analytics Guide {#using}

+ [Adobe Customer Journey Analytics Guide](../getting-started/cja-landing.md)
+ [AI Assistant for Adobe Customer Journey Analytics](../ai-assistant.md)
+ [Data Analysis AI Assistent for Customer Journey Analytics](../data-analysis-ai.md)

+ Release Notes {#releases}
  + [Latest release](../release-notes/latest.md)
  + [2024 releases](../release-notes/2024.md)
  + [2023 releases](../release-notes/2023.md)
  + [2022 releases](../release-notes/2022.md)
  + [2021 releases](../release-notes/2021.md)
  + [2020 releases](../release-notes/2020.md)
  + [Feature release strategy](../release-notes/releases.md)
  + [Documentation updates](../release-notes/doc-changes.md)

+ Getting Started {#cja-overview}
  + [Customer Journey Analytics overview](../getting-started/cja-overview.md)
  + [Quick start guide](../getting-started/cja-getting-started.md)
  + [Landing page](../getting-started/landing.md)
  + [Landing page (old)](../getting-started/cja-landing-old.md)
  + [Frequently asked questions](../getting-started/cja-faq.md)
  + [Compare Customer Journey Analytics to BI solutions](../getting-started/cja-vs-bi.md)

+ Customer Journey Analytics and Adobe Analytics {#compare-aa-cja}
  + Upgrade to Customer Journey Analytics {#upgrade-to-cja}
    + [Get started](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)
    + [Choose your upgrade path](/help/getting-started/cja-upgrade/cja-upgrade-path.md)
    + [Send data to Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)
    + [Retain historical data](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)
    + [Recommended process](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)
    + [Understand Analytics implementation](/help/getting-started/cja-upgrade/cja-upgrade-analytics-implementation.md)
    + [Create lookup datasets for classifications](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)
    + [Use tags to upgrade](/help/getting-started/cja-upgrade/cja-upgrade-websdk-tags.md)
    + [Architect your schema](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md)
    + [Create your schema](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)
    + [Use your existing schema](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)
    + [Create a dataset](/help/getting-started/cja-upgrade/cja-upgrade-dataset.md)
    + [Create a datastream](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md)
    + [Add Platform as a service](/help/getting-started/cja-upgrade/cja-upgrade-datastream-addplatform.md)
    + [Create a connection](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)
    + [Create a data view](/help/getting-started/cja-upgrade/cja-upgrade-dataview.md)
    + [Validate data flow](/help/getting-started/cja-upgrade/cja-upgrade-validate.md)
    + [Upgrade shortcut: Migrate to Web SDK](/help/getting-started/cja-upgrade/cja-upgrade-shortcut-websdk.md)
  + Comparison with Adobe Analytics {#cja-aa-comparison}
    + [Overview](../getting-started/aa-vs-cja/overview.md)
    + [Use Adobe Analytics data](../getting-started/aa-vs-cja/aa-data-in-cja.md)
    + [Feature support](../getting-started/aa-vs-cja/cja-aa.md)
    + [Compare terminology](../getting-started/aa-vs-cja/terminology.md)
    + [Compare data processing](../getting-started/aa-vs-cja/data-processing-comparisons.md)
    + [Environments](../getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
    + [Analytics processing versus Data Prep](../getting-started/aa-vs-cja/pr-vista-dataprep.md)
    + [Analytics Identities](../getting-started/aa-vs-cja/aaid-ecid-adc.md)
  + [Evolution from Adobe Analytics ](../getting-started/aa-to-cja.md)
  + [User Guide for Adobe Analytics users](../getting-started/aa-to-cja-user.md)

+ Data Ingestion {#cja-data-ingestion}
  + [Data ingestion overview](../data-ingestion/data-ingestion.md)
  + Ingest and use quick start guides{#ingest-use-guides}
    + [Adobe Analytics](../data-ingestion/analytics.md)
    + Experience Platform Edge Network {#edge-network}
      + [Web SDK](../data-ingestion/aepwebsdk.md)
      + [Mobile SDK](../data-ingestion/aepmobilesdk.md)
      + [Server API](../data-ingestion/serverapi.md)
    + [Batch data](../data-ingestion/batch.md)
    + [Streaming data](../data-ingestion/streaming.md)
    + [Source connectors](../data-ingestion/sources.md)

+ Connections {#cja-connections}
  + [Connections overview](../connections/overview.md)
  + [Create or edit a connection](../connections/create-connection.md)
  + [Manage connections](../connections/manage-connections.md)
  + [Combined event datasets](../connections/combined-dataset.md)
  + [Standard lookups](../connections/standard-lookups.md)
  + [B2B lookups](../connections/transform-datasets-b2b-lookups.md)

+ Data Views {#cja-dataviews}
  + [Data views overview](../data-views/data-views.md)
  + [Create or edit a data view](../data-views/create-dataview.md)
  + [Session settings](../data-views/session-settings.md)
  + Component Settings {#component-settings}
    + [Component settings overview](../data-views/component-settings/overview.md)
    + [Attribution](../data-views/component-settings/attribution.md)
    + [Behavior](../data-views/component-settings/behavior.md)
    + [Format](../data-views/component-settings/format.md)
    + [Include exclude values](../data-views/component-settings/include-exclude-values.md)
    + [Metric deduplication](../data-views/component-settings/metric-deduplication.md)
    + [No value options](../data-views/component-settings/no-value-options.md)
    + [Persistence](../data-views/component-settings/persistence.md)
    + [Substring](../data-views/component-settings/substring.md)
    + [Summary data group](../data-views/component-settings/summary-data-group.md)
    + [Value bucketing](../data-views/component-settings/value-bucketing.md)
  + [Standard component reference](../data-views/component-reference.md)
  + [BI extension](../data-views/bi-extension.md)
  + [Derived fields](../data-views/derived-fields/derived-fields.md)
  + [Summary data](../data-views/summary-data.md)
  + [Labels and policies](../data-views/data-governance.md)

+ Tools {#tools}
  + Asset Transfer {#asset-transfer}
    + [Transfer assets](../tools/asset-transfer/transfer-assets.md) 
  + Product Usage {#product-usage}
    + [Overview](../tools/product-usage/usage-overview.md)
    + [Data settings](../tools/product-usage/data-settings.md)
    + [Opt-out settings](../tools/product-usage/opt-out-settings.md)

+ Workspace projects {#cja-workspace}
  + [Analysis Workspace overview](../analysis-workspace/home.md)
  + [Perform basic analysis](../analysis-workspace/perform-basic-analysis.md)
  + [Perform advanced analysis](../analysis-workspace/perform-adv-analysis.md)
  + Projects {#build-workspace-project}
    + [Overview](../analysis-workspace/build-workspace-project/freeform-overview.md)
    + [Create projects](/help/analysis-workspace/build-workspace-project/create-projects.md)
    + [Open projects](/help/analysis-workspace/build-workspace-project/open-projects.md)
    + [Save projects](../analysis-workspace/build-workspace-project/save-projects.md)
    + Folders in Workspace {#workspace-folders}
      + [About folders](../analysis-workspace/build-workspace-project/workspace-folders/about-folders.md)
      + [Create folders and subfolders](../analysis-workspace/build-workspace-project/workspace-folders/create-folders.md)
      + [Manage folders](../analysis-workspace/build-workspace-project/workspace-folders/manage-folders.md)
      + [Add or move projects to folders](../analysis-workspace/build-workspace-project/workspace-folders/add-projects.md)
    + [Hotkeys (Shortcuts)](../analysis-workspace/build-workspace-project/fa-shortcut-keys.md)
    + [Color palettes](../analysis-workspace/build-workspace-project/color-palettes.md)
    + [View density](../analysis-workspace/build-workspace-project/view-density.md)
  + [Use templates](../analysis-workspace/templates/use-templates.md)
  + Visualizations {#visualizations}
    + [Overview](../analysis-workspace/visualizations/freeform-analysis-visualizations.md)
    + [Manage data sources](../analysis-workspace/visualizations/t-sync-visualization.md)
    + [Intelligent captions](../analysis-workspace/visualizations/intelligent-captions.md)
    + Freeform table {#freeform-table}
      + [Overview](../analysis-workspace/visualizations/freeform-table/freeform-table.md)
      + [Create hyperlinks](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)
      + Column and row settings {#column-row-settings}
        + [Column settings](../analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)
        + [Row settings](../analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)
        + [Dynamic and static items](../analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)
      + [Filter and sort tables](../analysis-workspace/visualizations/freeform-table/filter-and-sort.md)
      + [Workspace totals](../analysis-workspace/visualizations/freeform-table/workspace-totals.md)
    + Cohort Table {#cohort-table}
      + [Overview](../analysis-workspace/visualizations/cohort-table/cohort-analysis.md)
      + [Configure](../analysis-workspace/visualizations/cohort-table/t-cohort.md)
      + [Use cases](../analysis-workspace/visualizations/cohort-table/cohort-use-cases.md)
    + Fallout {#fallout}
      + [Overview](../analysis-workspace/visualizations/fallout/fallout-flow.md)
      + [Configure](../analysis-workspace/visualizations/fallout/configuring-fallout.md)
      + [Inter-dimensional fallout](../analysis-workspace/visualizations/fallout/configuring-interdimensional-fallout.md)
      + [Apply filters](../analysis-workspace/visualizations/fallout/compare-segments-fallout.md)
    + Flow {#flow}
      + [Overview](../analysis-workspace/visualizations/c-flow/flow.md)
      + [Configure](../analysis-workspace/visualizations/c-flow/create-flow.md)
      + [Inter-dimensional flows](../analysis-workspace/visualizations/c-flow/multi-dimensional-flow.md)
    + Journey canvas {#journey-canvas}
      + [Overview](../analysis-workspace/visualizations/journey-canvas/journey-canvas.md)
      + [Configure](../analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md)
      + [Troubleshoot](../analysis-workspace/visualizations/journey-canvas/journey-canvas-troubleshooting.md)
    + [Area (stacked)](../analysis-workspace/visualizations/area.md)
    + [Bar (stacked)](../analysis-workspace/visualizations/bar.md)
    + [Bullet](../analysis-workspace/visualizations/bullet-graph.md)
    + [Combo](../analysis-workspace/visualizations/combo-charts.md)
    + [Donut](../analysis-workspace/visualizations/donut.md)
    + [Histogram](../analysis-workspace/visualizations/histogram.md)
    + [Horizontal bar (stacked)](../analysis-workspace/visualizations/horizontal-bar.md)
    + [Key metric summary](../analysis-workspace/visualizations/key-metric.md)
    + [Line](../analysis-workspace/visualizations/line.md)
    + [Scatter](../analysis-workspace/visualizations/scatterplot.md)
    + [Summary number and change](../analysis-workspace/visualizations/summary-number-change.md)
    + [Section header](/help/analysis-workspace/visualizations/section-header.md)
    + [Text](../analysis-workspace/visualizations/text.md)
    + [Tree map](../analysis-workspace/visualizations/treemap.md)
    + [Venn](../analysis-workspace/visualizations/venn.md)
  + Panels {#panels}
    + [Overview](../analysis-workspace/c-panels/panels.md)
    + [Blank panel](../analysis-workspace/c-panels/blank-panel.md)
    + [Attribution](../analysis-workspace/c-panels/attribution.md)
    + [Experimentation](../analysis-workspace/c-panels/experimentation.md)
    + [Freeform](../analysis-workspace/c-panels/freeform-panel.md)
    + [Media average minute audience](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)
    + [Media concurrent viewers](../analysis-workspace/c-panels/media-concurrent-viewers.md)
    + [Media playback time spent](../analysis-workspace/c-panels/media-playback-time-spent.md)
    + [Next or previous item](../analysis-workspace/c-panels/next-previous.md)
    + [Quick insights](../analysis-workspace/c-panels/quickinsight.md)
  + Curate, Share and Schedule projects {#curate-share}
    + [Overview](../analysis-workspace/curate-share/send-schedule-files.md)
    + [Curate projects](../analysis-workspace/curate-share/curate.md)
    + [Share projects](../analysis-workspace/curate-share/share-projects.md)
    + [Create shareable links](../analysis-workspace/curate-share/shareable-links.md)
    + [View-only projects](../analysis-workspace/curate-share/view-only-projects.md)
  + Export {#export}
    + [Overview](../analysis-workspace/export/export-project-overview.md)
    + [Download](../analysis-workspace/export/download-send.md)
    + [Send to others](../analysis-workspace/export/t-schedule-report.md)
    + [Export to the cloud](../analysis-workspace/export/export-cloud.md)
  + Anomaly Detection {#anomaly-detection}
    + [Overview](../analysis-workspace/c-anomaly-detection/anomaly-detection.md)
    + [View anomalies](../analysis-workspace/c-anomaly-detection/view-anomalies.md)
    + [Statistical techniques](../analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md)
  + Forecasting {#forecasting}
    + [Overview](../analysis-workspace/c-forecast/forecasting.md)
    + [View forecasts](../analysis-workspace/c-forecast/view-forecasts.md)
    + [Statistical techniques](../analysis-workspace/c-forecast/statistics-forecasting.md)
  + [Table of contents](../analysis-workspace/build-workspace-project/project-table-of-contents.md)
  + [User preferences](../analysis-workspace/user-preferences.md)
  + Workspace FAQs and more {#workspace-faq}
    + [Frequently asked questions](../analysis-workspace/workspace-faq/faq.md)
    + [Error messages](../analysis-workspace/workspace-faq/error-messages.md)
    + [Limitations](../analysis-workspace/workspace-faq/aw-limitations.md)
    + [Administration requirements](../analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)
    + [Accessibility](../analysis-workspace/workspace-faq/aw-accessibility.md)

+ Analytics dashboards {#cja-dashboards}
  + [Overview](../mobile-app/home.md)
  + [Curator tasks](../mobile-app/curator.md)
  + [Create mobile scorecards](../mobile-app/create-scorecard.md)
  + [Manage mobile scorecards](../mobile-app/manage-scorecard.md)
  + [Set up executives to use dashboards](../mobile-app/set-up-execs.md)
  + [Executive user quick start guide](../mobile-app/executive.md)

+ Guided analysis {#guided-analysis}
    + [Overview](../guided-analysis/overview.md)
    + [Active growth](../guided-analysis/types/active-growth.md)
    + [Conversion trends](../guided-analysis/types/conversion-trends.md)
    + [Engagement](../guided-analysis/types/engagement.md)
    + [First use impact](../guided-analysis/types/first-use-impact.md)
    + [Frequency](../guided-analysis/types/frequency.md)
    + [Funnel](../guided-analysis/types/funnel.md)
    + [Net growth](../guided-analysis/types/net-growth.md)
    + [Release impact](../guided-analysis/types/release-impact.md)
    + [Retention](../guided-analysis/types/retention.md)
    + [Timeline](../guided-analysis/types/timeline.md)
    + [Trends](../guided-analysis/types/trends.md)
    + [Industry use cases](../guided-analysis/industry-use-cases.md)
    + [FAQ](../guided-analysis/faq.md)

+ Components {#cja-components}
  + [Overview](../components/overview.md)
  + [Use components in Analysis Workspace](../components/use-components-in-workspace.md)
  + [Add component descriptions](../components/add-component-descriptions.md)
  + Annotations {#annotations}
    + [Annotations overview](../components/annotations/overview.md)
    + [Create annotations](../components/annotations/create-annotations.md)
    + [Manage annotations](../components/annotations/manage-annotations.md)
    + [View annotations](../components/annotations/view-annotations.md)
    + [Mobile annotations](../components/annotations/mobile-annotations.md)
  + [Scheduled projects](../components/scheduled-projects-manager.md)
  + Audiences {#audiences}
    + [Audiences overview](../components/audiences/audiences-overview.md)
    + [Create and publish audiences](../components/audiences/publish.md)
    + [Manage audiences](../components/audiences/manage.md)
  + Dimensions {#dimensions}
    + [Dimensions overview](../components/dimensions/overview.md)
    + [Preview dimensions](../components/dimensions/view-dimensions.md)
    + [Break down dimensions](../components/dimensions/t-breakdown-fa.md)
    + [Time-parting dimensions](../components/dimensions/time-parting-dimensions.md)
    + [High cardinality dimensions](../components/dimensions/high-cardinality.md)
  + [Metrics](../components/apply-create-metrics.md)
  + Filters {#cja-filters}
    + [Overview](../components/filters/filters-overview.md)
    + [Create filters](../components/filters/create-filters.md)
    + [Build filters](../components/filters/filter-builder.md)
    + [Quick filters](../components/filters/quick-filters.md)
    + [Sequential filters](../components/filters/seg-sequential-build.md)
    + [Share filters](../components/filters/filters-share.md)
    + [Tag filters](../components/filters/filters-tag.md)
    + [Filter the list of filters](../components/filters/filters-filter.md)
    + [Mark filters as favorites](../components/filters/filters-favorite.md)
    + [Approve filters](../components/filters/filters-approve.md)
    + [Copy filters](../components/filters/filters-copy.md)
    + [Manage filters](../components/filters/manage-filters.md)
    + [Operators](../components/filters/operators.md)
  + Calculated metrics {#cja-calcmetrics}
    + [Overview](../components/calc-metrics/calc-metr-overview.md)
    + Calculated metrics workflow {#cm-workflow}
      + [Create calculated metrics](../components/calc-metrics/cm-workflow/cm-workflow.md)
      + [Build calculated metrics](../components/calc-metrics/cm-workflow/cm-build-metrics.md)
      + [Find metrics](../components/calc-metrics/cm-workflow/cm-finding.md)
      + [Metric type and attribution](../components/calc-metrics/cm-workflow/m-metric-type-alloc.md)
      + [Build a participation metric](../components/calc-metrics/cm-workflow/participation-metric.md)
      + [Filtered metrics](../components/calc-metrics/cm-workflow/metrics-with-segments.md)
      + [Stack and replace filters](../components/calc-metrics/cm-workflow/cm-stack-seg.md)
      + [Filter calculated metrics](../components/calc-metrics/cm-workflow/cm-filter.md)
      + [Mark calculated metrics as favorites](../components/calc-metrics/cm-workflow/cm-favorite.md)
      + [Copy calculated metrics](../components/calc-metrics/cm-workflow/cm-copy.md)
      + [Use functions](../components/calc-metrics/cm-workflow/cm-using-functions.md)
      + [Tag calculated metrics](../components/calc-metrics/cm-workflow/cm-tagging.md)
      + [Approve calculated metrics](../components/calc-metrics/cm-workflow/cm-approving.md)
      + [Share calculated metrics](../components/calc-metrics/cm-workflow/cm-sharing.md)
      + [Manage calculated metrics](../components/calc-metrics/cm-workflow/cm-manager.md)
      + [Examples](../components/calc-metrics/cm-workflow/cm-weighted-metric.md)
    + [Calculated metrics templates](../components/calc-metrics/default-calcmetrics.md)
    + [Basic functions](../components/calc-metrics/cm-functions.md)
    + [Advanced functions](../components/calc-metrics/cm-adv-functions.md)
  + Date ranges {#cja-date-ranges}
    + [Overview](../components/date-ranges/overview.md)
    + [Create date ranges](../components/date-ranges/create.md)
    + [Manage date ranges](../components/date-ranges/manage.md)
    + [Date comparison](../components/date-ranges/time-comparison.md)
    + [Examples](../components/date-ranges/custom-date-ranges.md)
  + Alerts {#alerts}
    + [Overview](/help/components/c-intelligent-alerts/intelligent-alerts.md) 
    + [Create alerts](/help/components/c-intelligent-alerts/alert-builder.md)
    + [Manage alerts](/help/components/c-intelligent-alerts/alert-manager.md)
    + [Feature comparison](/help/components/c-intelligent-alerts/alerts-feature-comparison.md)
    + [Use cases](/help/components/c-intelligent-alerts/alerts-use-cases.md)
  + Exports {#exports}
    + [Configure cloud export accounts](/help/components/exports/cloud-export-accounts.md)
    + [Configure cloud export locations](/help/components/exports/cloud-export-locations.md)
    + [Manage cloud export locations](/help/components/exports/manage-export-locations.md)
    + [Manage exports](/help/components/exports/manage-exports.md)
    + [Manage export logs](/help/components/exports/manage-export-logs.md)
    + [Troubleshoot exports](/help/components/exports/troubleshoot-exports.md)
  + Data Dictionary {#data-dictionary}
    + [Overview](../components/data-dictionary/data-dictionary-overview.md)
    + [View component information in the Data Dictionary](../components/data-dictionary/view-data-dictionary.md)
    + [Edit component entries in the Data Dictionary](../components/data-dictionary/edit-entries-data-dictionary.md)
    + [Monitor Data Dictionary health](../components/data-dictionary/monitor-data-dictionary-health.md)

+ Report Builder {#cja-reportbuilder}
  + [Overview](../report-builder/report-buider-overview.md)
  + [Report Builder Set Up](../report-builder/report-builder-setup.md)
  + [Create a Data Block](../report-builder/create-a-data-block.md)
  + [Report Builder Hub](../report-builder/report-builder-hub.md)
  + [Select a Data View](../report-builder/select-data-view.md)
  + [Select a Date Range](../report-builder/select-date-range.md)
  + [Work with Filters](../report-builder/work-with-filters.md)
  + [Filter Dimensions](../report-builder/filter-dimensions.md)
  + [Manage Data Blocks](../report-builder/manage-reportbuilder.md)
  + [Schedule Workbooks](../report-builder/schedule-reportbuilder.md)
  + [Restricted Labels](../report-builder/restricted-labels.md)
  + [Report Builder Settings](../report-builder/report-builder-settings.md)

+ Reporting Activity Manager {#reporting-activity-manager}
  + [Overview](../reporting-activity-manager/reporting-activity-overview.md)
  + [View reporting activity](../reporting-activity-manager/reporting-activity.md)
  + [Cancel reporting requests](../reporting-activity-manager/reporting-activity-cancel-requests.md)

+ Stitching {#stitching}
  + [Overview](../stitching/overview.md)
  + [Create and manage stitched datasets](../stitching/stitching-ui.md)
  + [Frequently Asked Questions](../stitching/faq.md)  

+ Adobe integrations {#integrations}
  + [Overview](/help/integrations/overview.md)
  + [Integrate Adobe Analytics](/help/integrations/aa.md)
  + [Integrate Target](/help/integrations/at.md)
  + [Integrate Journey Optimizer data](/help/integrations/ajo.md)
  + [Integrate Decision Management data](/help/integrations/ajo-od.md)
  + [Integrate Customer AI](/help/integrations/customer-ai.md)

+ Data Governance {#cja-privacy}
  + [Data Governance](../privacy/privacy-overview.md)
  + [Audit Log](../privacy/audit-log.md)
  + [Customer Managed Keys](../privacy/cmk.md)

+ Use cases {#cja-usecases}
  + [Customer Journey Analytics use cases](../use-cases/cja-usecases.md)
  + Google Analytics data {#ga}
    + [Migrate data from Google Analytics](../use-cases/ga/overview.md)
    + [Ingest Google Analytics historical data ](../use-cases/ga/backfill.md)
    + [Configure streaming Google Analytics data](../use-cases/ga/streaming.md)
    + [Report on Google Analytics data](../use-cases/ga/report.md)
  + Data ingestion {#data-ingestion}
    + [Ingest and use Marketo Engage data](../use-cases/data-ingestion/marketo.md)
    + [Ingest and use Experience Platform audiences ](../use-cases/data-ingestion/ingest-aep-segments.md)
  + Data views {#data-views}
    + [Data views use cases](/help/use-cases/data-views/data-views-usecases.md)
    + [Use binding dimensions and metrics](/help/use-cases/data-views/binding-dimensions-metrics.md)
    + [Use summary data](/help/use-cases/data-views/summary-data.md)
    + [BI extension use cases](/help/use-cases/data-views/bi-extension-usecases.md)
  + Data export {#data-export}
    + [Overview](../use-cases/data-export/overview.md)
    + [BI extension](../use-cases/data-export/bi-extension.md)
    + [Export datasets](../use-cases/data-export/export-datasets.md)
    + [Export full table](../use-cases/data-export/export-full-table.md)
    + [Query Service and Export datasets](../use-cases/data-export/queryservice-export-datasets.md)
  + B2B {#b2b}
    + [An example B2B project](../use-cases/b2b/example.md)
  + Cross-channel data {#cross-channel}
    + [Analyze data across channels](../use-cases/cross-channel/cross-channel.md)
    + [Import call center and web data](../use-cases/cross-channel/call-center.md)
  + Adobe Analytics data {#aa-data}
    + [Use Marketing channel dimensions](../use-cases/aa-data/marketing-channels.md)
    + [Combine report suites with different schemas](../use-cases/aa-data/combine-report-suites.md)
  + Complex data {#complex-data}
    + [Use arrays of objects](../use-cases/object-arrays.md)
  + Stitching {#stitching}
    + [Shared devices](/help/use-cases/stitching/shared-devices.md)
  + Derived fields {#derived-fields}
    + [Report on goals](../use-cases/goals-using-derived-fields.md)

+ Labs {#labs}
  + [Labs User Guide](../labs/labs.md)

+ Troubleshooting {#troubleshooting}
  + [Compare data](../troubleshooting/compare.md)
  + [Consistency of metrics and audiences](../troubleshooting/consistency-rcdp-cja.md)
  + [Lack of permissions](../troubleshooting/lack-of-permissions.md)

+ Tech notes {#technotes}
  + [Access Control](../technotes/access-control.md)
  + [Data centers](../technotes/data-centers.md)
  + [Deletion implications](../technotes/deletion.md)
  + [Domains](../technotes/domains.md)
  + [Glossary](../technotes/glossary.md)
  + [Guardrails](../technotes/guardrails.md)
  + [IP addresses](../technotes/ip-addresses.md)
  + [Optimize performance](../technotes/optimizing-performance.md)
  + [View and manage usage](../technotes/estimate-usage.md)

+ [Customer Journey Analytics API](https://developer.adobe.com/cja-apis/docs/)
