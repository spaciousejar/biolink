<template>
  <base-form-section
    title="Social Links"
    description="Add some social media links"
  >
    <div class="shadow sm:overflow-hidden sm:rounded-md">
      <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 bg-white px-4 py-5 sm:p-6">
        <div v-for="(link, index) in socialLinks" :key="index">
          <label :for="link.name" class="block text-sm font-medium text-gray-700">
            {{ link.label }}
          </label>
          <div class="mt-1 flex rounded-md shadow-sm">
            <span class="inline-flex items-center rounded-l-md border border-r-0 border-gray-300 bg-gray-50 px-3 text-sm text-gray-500">
              <icon :name="link.icon" class="w-5 h-5" />
            </span>
            <input
              type="search"
              :name="link.name"
              :id="link.name"
              :value="props[link.name]"
              @input="$emit(`update:${link.name}`, $event.target.value)"
              class="block w-full flex-1 rounded-none rounded-r-md border-gray-300 focus:border-indigo-500 focus:ring-indigo-500 sm:text-sm"
              :placeholder="link.placeholder"
            />
          </div>
        </div>
      </div>
    </div>
  </base-form-section>
</template>

<script setup>
const props = defineProps([
  "facebook",
  "twitter",
  "instagram",
  "linkedin",
  "github",
  "telegram",
  "whatsapp",
  "youtube",
  "email",
]);

const socialLinks = [
  { name: 'facebook', label: 'Facebook', icon: 'ph:facebook-logo-duotone', placeholder: 'https://fb.com/elonmusk' },
  { name: 'twitter', label: 'Twitter', icon: 'ph:twitter-logo-duotone', placeholder: 'https://twitter.com/elonmusk' },
  { name: 'instagram', label: 'Instagram', icon: 'ph:instagram-logo-duotone', placeholder: 'https://instagram.com/elonmusk' },
  { name: 'github', label: 'Github', icon: 'ph:github-logo-duotone', placeholder: 'https://github.com/elonmusk' },
  { name: 'telegram', label: 'Telegram', icon: 'ph:telegram-logo-duotone', placeholder: 'https://t.me/elonmusk' },
  { name: 'linkedin', label: 'Linkedin', icon: 'ph:linkedin-logo-duotone', placeholder: 'https://linkedin.com/elonmusk' },
  { name: 'email', label: 'Email', icon: 'ph:envelope-duotone', placeholder: 'elonmusk@geemail.com' },
  { name: 'youtube', label: 'Youtube', icon: 'ph:youtube-logo-duotone', placeholder: 'https://youtube.com/elonmusk' },
  { name: 'whatsapp', label: 'Whatsapp', icon: 'ph:whatsapp-logo-duotone', placeholder: '+9190000000000' },
];
</script>
