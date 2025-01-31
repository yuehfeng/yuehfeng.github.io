<template>
    <div class="container">
        <ContactInformation />
        <EducationComponent />
        <ProfessionComponent />
        <WorkExperience />
        <CertificationCompetition />
    </div>
    <FooterComponent />
</template>

<script>
import ContactInformation from "@/components/ContactInformation.vue";
import EducationComponent from "@/components/EducationComponent.vue";
import ProfessionComponent from "@/components/ProfessionComponent.vue";
import WorkExperience from "@/components/WorkExperience.vue";
import CertificationCompetition from "@/components/CertificationCompetition.vue";
import FooterComponent from "@/components/FooterComponent.vue";

export default {
    name: "HomeView",
    components: {
        ContactInformation,
        EducationComponent,
        ProfessionComponent,
        WorkExperience,
        CertificationCompetition,
        FooterComponent
    },
};
</script>
