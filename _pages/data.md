---
layout: default
title: SATIN Public Leaderboard
---

# SATIN Public Leaderboard 2

This is the public leaderboard for the SATIN metadataset benchmark. The leaderboard shows the performance of different models and algorithms on our remote sensing imagery datasets.

| Rank | Team Name       | Model         | Score  | Submission Date |
|------|-----------------|---------------|--------|-----------------|
{% for entry in site.data.leaderboard %}
| {{ forloop.index }}   | {{ entry.team_name }} | {{ entry.model }} | {{ entry.score }} | {{ entry.submission_date }} |
{% endfor %}
