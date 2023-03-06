<script setup>
import { Head, Link } from '@inertiajs/vue3';
import ApplicationMark from '@/Components/ApplicationMark.vue';
import Section from '@/NewComponents/Section.vue';
import Button from '@/NewComponents/Button.vue';
import Skill from '@/NewComponents/Skill.vue';

defineProps({
    canLogin: Boolean,
    canRegister: Boolean,
    skills: Object,
});
</script>

<template>
    <Head  title="Welcome"/>

    <div class="grid grid-cols-2 text-right py-10 px-72 bg-gray-800 text-gray-300">
            <div>
                <ApplicationMark class="h-12= x-auto"></ApplicationMark>
            </div>

            <div v-if="canLogin">
                <Link v-if="$page.props.user" :href="route('dashboard')" class="text-sm underline">
                    Dashboard
                </Link>

                <template v-else>
                    <Link :href="route('login')" class="text-base underline">
                        Log in
                    </Link>

                    <Link v-if="canRegister" :href="route('register')" class="text-basd underline place-self-end ml-4">
                        Register
                    </Link>
                </template>
            </div>
    </div>

    <Section class="bg-gray-800 pt-16 h-screen">
        <div class="h-2/3 flex-wrap content-between border-gray-600 pb-36 ">
            <p class="border-b-2 font-bold border-gray-400 pb-3 text-2xl text-gray-300 uppercase">Hey! This is Juan. I'm a Full Stack Developer and I would like to work with you.</p>
            <div class="flex items-end border-b-2 border-gray-500 pb-2">
                <p class="fornbold mr-5 text-gray-500 text-xl">Want to know more?</p>
                <Button>
                    Let's Chat
                </Button>
            </div>
        </div>

        <div class="animate-pulse mt-3 text-grtay-300 text-center text-9xl">
            <a href="#skills">&#8675;</a>
        </div>

    </Section>

    <Section id="skills" class="bg-gray-200 text-gray-800 h-screen">
        <h2 class="text-6xl font-bold pt-3">Skills</h2>

        <div class="grid grid-cols-2">
            <div v-for="skill in skills" :key="skill.id">
                <Skill :background="skill.color">
                    {{  skill.name }}
                </Skill>
            </div>
        </div>

        <div class="flex justify-center mt-10">
            <Button>
                Get in touch
            </Button>
        </div>
    </Section>

    <Section class="bg-gray-600 text-gray-800 h-screen">
        <h2 class="text-6xl font-bold pt-3">Projects</h2>
        <div class="flex justify-center mt-10">
            <Button>
                Know more
            </Button>
        </div>
    </Section>

    <Section class="flex justify-between bg-grey-8000 text-gray-300 text-xl">
        <p>&copy; JuanMAdell. All rights reserved.</p>
        <div class="flex justify-evenly items-center">
            Github
            Facebook
            Linkedin
        </div>
    </Section>

    <div class="max-w-6xl mx-auto sm:px-6 lg:px-8">
        <div class="flex justify-center pt-8 sm:justify-start sm:pt-0">
            Welcome
        </div>
    </div>
</template>

