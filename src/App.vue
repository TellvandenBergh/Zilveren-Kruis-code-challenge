<template>
    <div id="app" class="main-placeholder">
        <!-- HEADER -->
        <FormHeader />
        <!-- CONTENT HERE -->
        <div class="container my-3">
            <div class="row">
                <form @submit="checkForm">
                    <div class="col-8">
                        <PageHeader title="Aanmelden" />
                        <SectionHeader title="Gegevens" />

                        <div class="form-group">
                            <ParagraphHeader title="Reden van aanmelding" />
                            <OptionSelector
                                title="Wat is de reden van uw aanvraag?"
                                :options="[
                                    'Nieuwe werkgever met collectiviteit bij Zilveren Kruis',
                                    'Overstappen per 1-1-2023 naar Zilveren Kruis'
                                ]"
                            />
                        </div>
                        <div class="form-group">
                            <ParagraphHeader title="Persoonlijke gegevens" />
                            <InputField v-model="form.name" label="Naam" />
                            <InputField
                                v-model="form.infixes"
                                label="Tussenvoegsels"
                            />
                            <InputField
                                v-model="form.lastName"
                                label="Achternaam"
                            />
                            <RadioSelector
                                v-model="form.sex"
                                title="Geslacht"
                                :options="['Man', 'Vrouw']"
                            />
                            <InputField
                                v-model="form.dateOfBirth"
                                label="Geboortedatum"
                                type="date"
                            />
                            <InputField
                                v-model="form.bsn"
                                label="Burgerservicenummer"
                                :isValid="isValid.bsn"
                                errorMessage="Helaas is het ingevoerde burgerservicenummer niet geldig. Probeer het opnieuw."
                            />
                        </div>

                        <SectionHeader title="Verzekering" />

                        <div class="form-group">
                            <ParagraphHeader title="Basisverzekering" />
                            <p>
                                In Nederland is de basisverzekering verplicht.
                                Iedereen wordt voor de basisverzekering
                                geaccepteerd. De overheid bepaalt welke zorg
                                hierin zit en dit is dus bij elke verzekeraar
                                hetzelfde.
                            </p>
                            <CustomRadioSelector />
                        </div>
                        <div class="form-group">
                            <OptionSelector
                                title="Kies je betaaltermijn"
                                :options="[
                                    'per maand',
                                    'per kwartaal',
                                    'per jaar'
                                ]"
                            />
                        </div>
                        <div class="form-group">
                            <h3>Eigen risico</h3>
                            <div class="form-input my-4">
                                <div class="input__group">
                                    <label class="input__title">
                                        Kies de hoogste van het eigen risico
                                    </label>
                                    <select class="form-control">
                                        <option>
                                            € 385 - verplicht eigen risico
                                        </option>
                                        <option>
                                            € 885 - korting van € 22 per jaar
                                        </option>
                                    </select>
                                </div>
                            </div>
                        </div>
                        <div class="form-group">
                            <h3>Aanvullende verzekering</h3>
                            <p>
                                Onze aanvullende verzekeringen kennen ruim 100
                                verschillende vergoedingen. De hoogte van de
                                vergoeding verschilt per pakket.hoogte van de
                                vergoeding verschilt per pakket
                            </p>
                            <div class="form-input my-4">
                                <div class="input__group">
                                    <label class="input__title">
                                        Kies uw aanvullende verzekering
                                    </label>
                                    <select class="form-control">
                                        <option selected>
                                            Geen aanvullende verzekering
                                            geselecteerd
                                        </option>
                                        <option>
                                            Aanvullend 1 - € 21,38 per jaar
                                        </option>
                                        <option>
                                            Aanvullend 2 - € 85,06 per jaar
                                        </option>
                                        <option>
                                            Aanvullend 3 - € 198,63 per jaar
                                        </option>
                                        <option>
                                            Aanvullend 4 - € 359,73 per jaar
                                        </option>
                                    </select>
                                </div>
                            </div>
                        </div>
                        <div class="form-group">
                            <div class="form-input my-4">
                                <div class="input__group">
                                    <label class="input__title">
                                        Kies uw tandartsverzekering
                                    </label>
                                    <select class="form-control">
                                        <option selected>
                                            Geen tandartsverzekering
                                            geselecteerd
                                        </option>
                                        <option>
                                            Tand 1 - € 80,28 per jaar
                                        </option>
                                        <option>
                                            Tand 2 - € 221,65 per jaar
                                        </option>
                                        <option>
                                            Tand 3 - € 449,36 per jaar
                                        </option>
                                    </select>
                                </div>
                            </div>
                        </div>

                        <h2 class="mt-5">Controleren</h2>
                        <div class="form-group">
                            <h3>Gekozen pakket</h3>
                        </div>
                        <div class="form-group">
                            <h3>Totaalpremie</h3>
                        </div>
                        <div class="form-group">
                            <h3>Adres en contactgegevens</h3>
                        </div>
                    </div>
                    <div class="col-4">
                        <div class="card card--filled-secondary h-auto">
                            <div class="card-body">
                                <div class="sf-contactblok-content">
                                    <h3 class="mb-2">We staan voor je klaar</h3>
                                    <p class="mb-5">
                                        Twijfel je? Heb je een vraag?
                                    </p>
                                    <div class="phonenumber mb-2">
                                        <a href="tel:0900 040 03 09">
                                            <span class="sr-only">
                                                Telefoonnummer
                                            </span>
                                            0900 040 03 09
                                        </a>
                                        <div class="popover__container ml-1">
                                            <button
                                                id="info-phone"
                                                type="button"
                                                class="btn popover__btn btn--popover btn-none"
                                            >
                                                <span class="sr-only">
                                                    Informatie weergeven
                                                </span>
                                            </button>
                                        </div>
                                    </div>
                                    <small>
                                        Open op maandag t/m vrijdag van 08:00
                                        tot 17:00
                                    </small>
                                </div>
                            </div>
                        </div>
                    </div>
                    <button type="submit">SUBMIT</button>
                </form>
            </div>
        </div>

        <FormFooter />
    </div>
</template>

<script>
import FormHeader from '../components/global/FormHeader.vue';
import FormFooter from '../components/global/FormFooter.vue';
import PageHeader from '../components/headers/PageHeader.vue';
import SectionHeader from '../components/headers/SectionHeader.vue';
import ParagraphHeader from '../components/headers/ParagraphHeader.vue';
// import InputLabel from '../components/headers/InputLabel.vue';
import OptionSelector from '../components/Input/OptionSelector.vue';
import InputField from '../components/Input/InputField.vue';
import RadioSelector from '../components/Input/RadioSelector.vue';
import CustomRadioSelector from '../components/Input/CustomRadioSelector.vue';
export default {
    name: 'App',
    components: {
        FormHeader,
        FormFooter,
        PageHeader,
        SectionHeader,
        ParagraphHeader,
        // InputLabel,
        OptionSelector,
        InputField,
        RadioSelector,
        CustomRadioSelector
    },
    data() {
        return {
            form: {
                name: null,
                infixes: null,
                lastName: null,
                sex: null,
                dateOfBirth: null,
                bsn: null
            },
            isValid: {
                bsn: null
            }
        };
    },
    methods: {
        checkForm: function (e) {
            this.isValid.bsn = /^(\d{8}|\d{9})$/.test(this.form.bsn);

            e.preventDefault();
        }
    }
};
</script>

<style lang="scss"></style>
