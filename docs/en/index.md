---
layout: page
title: "YukiSU"
pageClass: landing-page
sidebar: false
outline: false
aside: false
---

<script setup lang="ts">
const hero = {
  badge: 'The ultimate Android root solution, so good even my fork is embarrassed',
  title: 'YukiSU',
  subtitle: 'Powerful? kernel-level root access, security compromised',
  description: 'Experience the next generation of Android root management.',
  logo: '/logo.svg',
  primary: { label: 'Get Started', href: '/guide/installation' },
  secondary: { label: 'View on GitHub', href: 'https://github.com/Anatdx/YukiSU' },
  metrics: [
    { label: 'Active users', value: '1+' },
    { label: 'Supported devices', value: '1+' },
    { label: 'GitHub stars', value: '0+' },
    { label: 'Community members', value: '1+' }
  ]
}

const features = {
  title: 'Why choose YukiSU',
  description: 'Where is security, performance, and reliability? All built around kernel-level root.',
  items: [
    {
      title: 'Non-GKI kernel support',
      body: 'Non-GKI/Pre-GKI kernel support from 4.x - 5.4 with LTS mode (3.x is experimental)',
      icon: 'arcticons:kernelsu',
      accent: 'teal'
    },
    {
      title: 'Based On Magic Mount',
      body: 'This has been replaced by metamodule',
      icon: 'solar:zip-file-outline',
      accent: 'blue'
    },
    {
      title: 'Support for KPM kernel modules',
      body: 'KPM modules support ported from Apatch but there are not many modules',
      icon: 'solar:download-bold',
      accent: 'indigo'
    },
    {
      title: 'Design it in your way',
      body: 'Customizable background, manage some susfs features, and adjust DPI etc.',
      icon: 'tabler:brush',
      accent: 'cyan'
    },
    {
      title: 'WebUI X',
      body: 'Next generation of webui implementation by MMRL supported',
      icon: 'arcticons:mmrl',
      accent: 'sky'
    },
    {
      title: 'Frequent updates',
      body: 'Actively maintained, contributors constantly bring improvements, fixes, and build failures',
      icon: 'solar:smartphone-update-bold-duotone',
      accent: 'violet'
    }
  ]
}

const steps = {
  title: 'Ready in three steps',
  description: "Unlock your device's full potential in minutes:",
  tag: 'Installation',
  commands: [
    'adb reboot recovery',
    'adb sideload kernel.zip',
    '# Flash the kernel zip in recovery mode'
  ],
  success: 'Installation complete! Reboot and enjoy.',
  primary: { label: 'Read full documentation' },
  secondary: { label: 'Download latest release', href: 'https://github.com/Anatdx/YukiSU/releases' }
}

const footer = {
  name: 'YukiSU',
  description: 'Next-generation root solution for Android devices: modern architecture, enhanced security, blazing-fast performance.',
  links: [
    {
      title: 'Resources',
      items: [
        { label: 'Documentation', href: '/guide/' },
        { label: 'GitHub Repository', href: 'https://github.com/Anatdx/YukiSU' },
        { label: 'Downloads', href: 'https://github.com/Anatdx/YukiSU/releases' },
        { label: 'Report Issues', href: 'https://github.com/Anatdx/YukiSU/issues' }
      ]
    },
    {
      title: 'Community',
      items: [
        { label: 'Telegram Channel', href: 'https://t.me/yukisu_chat' },
        { label: 'Discussions', href: 'https://github.com/Anatdx/YukiSU/discussions' },
        { label: 'Contributing', href: 'https://github.com/Anatdx/YukiSU/blob/main/CONTRIBUTING.md' },
        { label: 'License', href: 'https://github.com/Anatdx/YukiSU/blob/main/LICENSE' }
      ]
    }
  ],
  copyright: '© 2025 Anatdx. All rights reserved.',
  build: 'Built with ♥ using VitePress'
}
</script>

<LandingPage
  :hero="hero"
  :features="features"
  :steps="steps"
  :footer="footer"
/>